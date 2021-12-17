# framework-playbook
Ansible Playbook for [Framework laptop](https://frame.work/) basic setup

This is a project inspired by [Jeff Geerling](https://github.com/geerlingguy)'s [mac-dev-playbook](https://github.com/geerlingguy/mac-dev-playbook).
I want to be able to setup my Framework laptop for my Ubuntu working environment with code.
Since probably all the Framework notebook owner's going to face similar issues while installing the required packages for Linux environment, so I think it makes sense to open source it.

## My hardware & environment (tested)

For now I only run this ansible playbook against my own notebook. It may not work for your distro or hardware, please use it at your own risk. Here's my environment:

- **Distro**: Ubuntu Budgie 21.10
- **Wifi**: Intel® Wi-Fi 6E AX210 No vPro®

## Usage

Install ansible via pip

```bash
sudo apt install git python3-pip
pip3 install ansible --user
```

Ensure you have `~/.local/bin` in your `PATH` environemtn variable, then checkout the code

```bash
git clone https://github.com/fangpenlin/framework-playbook.git
cd framework-playbook
ansible-playbook main.yaml -K
```

Tags can be added, for example, say if you only want to install fingerprint reader, you can ru

```bash
ansible-playbook main.yaml -K -t fprint
```

or if you only want to install Wifi firmware

```bash
ansible-playbook main.yaml -K -t wifi
```

I followed the Ubuntu setup guide [here](https://community.frame.work/t/ubuntu-21-04-on-the-framework-laptop/2722) for the Wifi firmware. But later realized that my Ubuntu comes with a newer WiFi driver supports Intel® Wi-Fi 6 AX210 already, so you may not need to install the WiFi firmware.
