# toy-role
A configuration run by toy-config

Files:
runbook.yml - required file. Describes tasks to configure a server. Must contain the
following top level fields:
    runbook_name : Descriptive name.
    
    comments : Can be empty
    
    attributes : Variables for template substitution. If this were more than a code challenge, it would
            be possible to override the defaults through various means.
            
    tasks : List of actions to configure the role. Executed serially from top to bottom. Actions include


Here is an example role file:

```
runbook_name : Descriptive name

comments : Optional comments

attributes :
  key : value
  key2 :
    subkey : value

tasks :

- name : Descriptive name
  action : commands
  commands:
  - a list of shell commands
  - executed in order

- name : Descriptive name
  action : file
  source : location relative to files directory at top level of repo
  destination : full path on target system.
  owner : root
  group : root
  mode : 0750


- name : Descriptive name
  action : template
  source : telplate file relative to templates directory at top level of repo
  destination : Full path and filename on target system

```
