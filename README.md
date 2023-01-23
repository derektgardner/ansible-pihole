# Ansible Config for Pihole (Docker)

I use [pihole](https://github.com/pi-hole/docker-pi-hole) in a high availability setting using [Keepalived](https://keepalived.readthedocs.io/en/latest/) with rsync keeping the configurations the same on all instances. 

This is the configuration I've made for [Ansible](https://www.ansible.com/) to set it up. It's part of my process to get my homelab setup using [Infrastructure as Code](https://en.wikipedia.org/wiki/Infrastructure_as_code) principles. It will set up pihole (with the lists I use), keepalived and set a cron job to sync the instances.

I am constantly learning, and I am in no way an expert. I welcome any feedback you have on this repository.

## Pre-Requisites

1. A debian-based system such as Ubuntu or Raspbian.
2. Ansible installed on the machine you'll be issuing commands from.

## Instructions

1. Copy `example.inventory.yaml` to `inventory.yaml` and edit the file with your values.
2. Copy `example.config.yaml` to `config.yaml` and edit the file with your values.
3. Run the `main.ansible.yaml` playbook.

## Notes

I tie my docker containers to specific releases of what I'm pulling. If you'd rather have the latest release, comment out the image line in `templates/pihole-docker-compost.yaml.j2` with the specific release in it, and uncomment the image line with latest in it.