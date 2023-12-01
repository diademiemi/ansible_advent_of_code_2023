Advent of Code 2023, in Ansible!
================================

This repository contains my solutions to the [Advent of Code 2023](https://adventofcode.com/2023) challenges!  

## [Results](#results)
Day | Name | Stars | Reaction | Time to run
----|------|:-----:|:---------:|-----------:
[1](./roles/day1/tasks/main.yml) | [Trebuchet?!](https://adventofcode.com/2023/day/1) | ⭐ ⭐ | 🫠 | 43s
[2](./roles/day2/tasks/main.yml) | [](https://adventofcode.com/2023/day/2) | | |
[3](./roles/day3/tasks/main.yml) | [](https://adventofcode.com/2023/day/3) | | |
[4](./roles/day4/tasks/main.yml) | [](https://adventofcode.com/2023/day/4) | | |
[5](./roles/day5/tasks/main.yml) | [](https://adventofcode.com/2023/day/5) | | |
[6](./roles/day6/tasks/main.yml) | [](https://adventofcode.com/2023/day/6) | | |
[7](./roles/day7/tasks/main.yml) | [](https://adventofcode.com/2023/day/7) | | |
[8](./roles/day8/tasks/main.yml) | [](https://adventofcode.com/2023/day/8) | | |
[9](./roles/day9/tasks/main.yml) | [](https://adventofcode.com/2023/day/9) | | |
[10](./roles/day10/tasks/main.yml) | [](https://adventofcode.com/2023/day/10) | | |
[11](./roles/day11/tasks/main.yml) | [](https://adventofcode.com/2023/day/11) | | |
[12](./roles/day12/tasks/main.yml) | [](https://adventofcode.com/2023/day/12) | | |
[13](./roles/day13/tasks/main.yml) | [](https://adventofcode.com/2023/day/13) | | |
[14](./roles/day14/tasks/main.yml) | [](https://adventofcode.com/2023/day/14) | | |
[15](./roles/day15/tasks/main.yml) | [](https://adventofcode.com/2023/day/15) | | |
[16](./roles/day16/tasks/main.yml) | [](https://adventofcode.com/2023/day/16) | | |
[17](./roles/day17/tasks/main.yml) | [](https://adventofcode.com/2023/day/17) | | |
[18](./roles/day18/tasks/main.yml) | [](https://adventofcode.com/2023/day/18) | | |
[19](./roles/day19/tasks/main.yml) | [](https://adventofcode.com/2023/day/19) | | |
[20](./roles/day20/tasks/main.yml) | [](https://adventofcode.com/2023/day/20) | | |
[21](./roles/day21/tasks/main.yml) | [](https://adventofcode.com/2023/day/21) | | |
[22](./roles/day22/tasks/main.yml) | [](https://adventofcode.com/2023/day/22) | | |
[23](./roles/day23/tasks/main.yml) | [](https://adventofcode.com/2023/day/23) | | |
[24](./roles/day24/tasks/main.yml) | [](https://adventofcode.com/2023/day/24) | | |
[25](./roles/day25/tasks/main.yml) | [](https://adventofcode.com/2023/day/25) | | |

Times are for the real inputs, on a Ryzen 9 7950X with 64GB of CL30 RAM.  
I had previously run some of these on a Ryzen 5 5600X, it seems the 7950X is about 33% faster.  

The "Reaction" column is how I felt about the puzzle and how hellish it was to solve in Ansible.  

## [How to run](#how-to-run)
The Ansible code will run completely in memory on the local machine, so no need to configure hosts.  

To run the code, you will need to have Ansible installed. You can install it with `pip install ansible jmespath`.  

Then, you can run the code with `ansible-playbook playbooks/all.yml`.  

This will only use the example inputs given by advent of code, these are quite small and shouldn't take too long to run.  
To use the real inputs I was given, run the command again and add `-i inputs`. The inputs are located in files in `inputs/group_vars/all/day*.yml`.  

| :exclamation:  Real inputs are very large and may take several hours to process   |
|-----------------------------------------------------------------------------------|

Then, you can run the code with `ansible-playbook playbooks/all.yml -i inputs`.  

### [Running specific days](#running-specific-days)
To limit it to specific days you can use tags. Some days can take a while, Ansible was never meant to be used like this! :​)

For example, to run only day 1, you can run `ansible-playbook playbook.yml --tags day1`.  

## [Info](#info)
You can find more on Ansible filters here: [Ansible Filters documentation](https://docs.ansible.com/ansible/latest/user_guide/playbooks_filters.html).  
This is not a comprehensive list, and Ansible Collections can include more filters. Check [#goals](#goals) for which filters I will use.  

The following Jinja2 Filters are also available: [List of Jinja2 filters](https://jinja.palletsprojects.com/en/3.1.x/templates/#list-of-builtin-filters).  

While the filters and Jinja2 templating engine is primarily made to write configuration files, it is available in-line in Ansible tasks. Ansible's flow control statements interpret the input as a Jinja2 template, which is what allows for most of the flexibility you see here. Any text put inside Jinja2 delimiters will be interpreted as Jinja2 for any text, this allows for data manipulation and finer flow control.  

## [License](#license)
The code is licensed under the MIT license, feel free to take inspiration
