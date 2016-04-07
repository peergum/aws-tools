# aws-tools
Quick tools to simplify your interactions with amazon AWS

_This is a work in progress_

## INSTALL

###1. You will need aws-cli:
- Ubuntu/debian: `apt-get install aws-cli`
- Fedora/Others: `yum install aws-cli`

###2. CLI setup

You need to configure your aws CLI with your credentials
(get them from Travis if not already done, if you lost them,
you'll have to regenerate them, it's a good idea to save them locally)

Run `aws configure` which will ask for the key and secret and default settings
like the default region (us-west-2 is a good option) and the default output format
(text or json, depends on your usage)

###3. Clone this repo

```
cd
git clone git@github.com:peergum/aws-tools.git
```
will add aws-tools in your home folder

###4. Update your PATH

To run the scripts, add the following line at the end of your `.bashrc`
or `.bash_profile` scripts:

```
export PATH=$PATH:$HOME/aws-tools/bin
```

source the script (`. ~/.bashrc` or `. ~/.bash_profile`) or open a new
terminal window to get the new PATH into your session

## TOOLS

### bin/gethosts

Get the list of your active hosts, based on stage, name, route53 and elastic load balancer configurations

Syntax: `gethosts [-s stage] [type]`

`stage` would be anything that appears in the ELB name, like `prod`, `beta`, etc...
`type` is the type of host: `app`, `messaging`, etc...

default stage is `prod`, default type is all hosts
