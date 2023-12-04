Advent of Code 2023, in Ansible!
================================

This repository contains my solutions to the [Advent of Code 2023](https://adventofcode.com/2023) challenges!  

I am using Ansible to solve the challenges, because I can. 

... Actually, that's bold. I probably can't, this is a stupid idea.

For those who don't know, Ansible is a configuration management tool. It is used to configure servers, and is usually used to write configuration files. It is NOT meant to solve math puzzles!
Nonetheless, it features a powerful templating engine powered by Jinja2 and a lot of filters, which allow it to do logic and data manipulation. I'm hoping this will be enough to solve the challenges.

I don't expect this to be finished every day, this takes me at least an hour every day, and while I'd love to do this every day, that's not realistic. My hope is to catch up throughout January and finish the challenge before the next one starts, but we'll see how that goes.

## [Goals](#goals)
I want this to actually be solving Advent of Code in Ansible, not using Ansible to call Python modules, shell scripts or other external programs. I find that cheating, I want this to be pure Ansible.

For this reason I will try to use the Ansible Collections `ansible.builtin`, `ansible.utils` and `community.general` for modules and filters as much as possible. I will be banning `shell` and `command` modules, those are a cop-out.

This means the bulk of the operations will be done with `ansible.builtin.set_fact`, which just allows you to set a variable. Combined with many `loops`, `whens`, `untils` and other Ansible magic, this hopefully allows enough logic! This repository will likely end up containing a lot of Jinja2 statements that I hope will end up being useful to know outside of this challenge.

## [Results](#results)
Day | Challenge | Stars | Reaction | Time to run
----|------|:-----:|:---------:|-----------:
[Day 1](./roles/day1/tasks/main.yml) | [Trebuchet?!](https://adventofcode.com/2023/day/1) | ⭐ ⭐ | 🫠 | 24.18s
[Day 2](./roles/day2/tasks/main.yml) | [Cube Conundrum](https://adventofcode.com/2023/day/2) | ⭐ ⭐ | 😃 | 3.43s
[Day 3](./roles/day3/tasks/main.yml) | [Gear Ratios](https://adventofcode.com/2023/day/3) | ⭐ ⭐ | 😵😵😵 | 6h 58m 26.30s
[Day 4](./roles/day4/tasks/main.yml) | [Scratchcards](https://adventofcode.com/2023/day/4) | ⭐ ⭐ | 😀...🤯 | 7.29s
[Day 5](./roles/day5/tasks/main.yml) | [](https://adventofcode.com/2023/day/5) | | |
[Day 6](./roles/day6/tasks/main.yml) | [](https://adventofcode.com/2023/day/6) | | |
[Day 7](./roles/day7/tasks/main.yml) | [](https://adventofcode.com/2023/day/7) | | |
[Day 8](./roles/day8/tasks/main.yml) | [](https://adventofcode.com/2023/day/8) | | |
[Day 9](./roles/day9/tasks/main.yml) | [](https://adventofcode.com/2023/day/9) | | |
[Day 10](./roles/day10/tasks/main.yml) | [](https://adventofcode.com/2023/day/10) | | |
[Day 11](./roles/day11/tasks/main.yml) | [](https://adventofcode.com/2023/day/11) | | |
[Day 12](./roles/day12/tasks/main.yml) | [](https://adventofcode.com/2023/day/12) | | |
[Day 13](./roles/day13/tasks/main.yml) | [](https://adventofcode.com/2023/day/13) | | |
[Day 14](./roles/day14/tasks/main.yml) | [](https://adventofcode.com/2023/day/14) | | |
[Day 15](./roles/day15/tasks/main.yml) | [](https://adventofcode.com/2023/day/15) | | |
[Day 16](./roles/day16/tasks/main.yml) | [](https://adventofcode.com/2023/day/16) | | |
[Day 17](./roles/day17/tasks/main.yml) | [](https://adventofcode.com/2023/day/17) | | |
[Day 18](./roles/day18/tasks/main.yml) | [](https://adventofcode.com/2023/day/18) | | |
[Day 19](./roles/day19/tasks/main.yml) | [](https://adventofcode.com/2023/day/19) | | |
[Day 20](./roles/day20/tasks/main.yml) | [](https://adventofcode.com/2023/day/20) | | |
[Day 21](./roles/day21/tasks/main.yml) | [](https://adventofcode.com/2023/day/21) | | |
[Day 22](./roles/day22/tasks/main.yml) | [](https://adventofcode.com/2023/day/22) | | |
[Day 23](./roles/day23/tasks/main.yml) | [](https://adventofcode.com/2023/day/23) | | |
[Day 24](./roles/day24/tasks/main.yml) | [](https://adventofcode.com/2023/day/24) | | |
[Day 25](./roles/day25/tasks/main.yml) | [](https://adventofcode.com/2023/day/25) | | |

The "Reaction" column is a quick emoji summary of my reaction to the challenge!

Times are for the real inputs, on a Ryzen 9 7950X with 64GB of CL30 RAM with the command:
```bash
time ansible-playbook playbooks/all.yml -i inputs --tags dayX
```

## [How to run](#how-to-run)
The Ansible code will run completely in memory on the local machine, so no need to configure hosts.  

To run the code, you will need to have Ansible installed. You can install it with `pip install ansible jmespath`.  

Then, you can run the code with `ansible-playbook playbooks/all.yml`.  

This will only use the example inputs given by advent of code, these are quite small and shouldn't take too long to run.  
To use the real inputs I was given, run the command again and add `-i inputs`. The inputs are located in files in `inputs/group_vars/all/day*.yml`.  

| :exclamation:  Real inputs are very large and may take several hours to process on some days  |
|-----------------------------------------------------------------------------------------------|

Then, you can run the code with `ansible-playbook playbooks/all.yml -i inputs`.  

### [Running specific days](#running-specific-days)
To limit it to specific days you can use tags. Some days can take a while, Ansible was never meant to be used like this! :​)
Last year I even had a day that took 4 hours to run, and I'm expecting this year to be worse.

For example, to run only day 1, you can run `ansible-playbook playbook.yml --tags day1`.  

## [Info](#info)
You can find more on Ansible filters here: [Ansible Filters documentation](https://docs.ansible.com/ansible/latest/user_guide/playbooks_filters.html).  
This is not a comprehensive list, and Ansible Collections can include more filters. Check [#goals](#goals) for which filters I will use.  

The following Jinja2 Filters are also available: [List of Jinja2 filters](https://jinja.palletsprojects.com/en/3.1.x/templates/#list-of-builtin-filters).  

While the filters and Jinja2 templating engine is primarily made to write configuration files, it is available in-line in Ansible tasks. Ansible's flow control statements interpret the input as a Jinja2 template, which is what allows for most of the flexibility you see here. Any text put inside Jinja2 delimiters will be interpreted as Jinja2 for any text, this allows for data manipulation and finer flow control.  

## [License](#license)
The code is licensed under the [CC-0 license](./LICENSE), making it public domain. Feel free to take inspiration from this shit. I really don't care, this is such a waste of my time that if someone else can gain from it, feel free!
