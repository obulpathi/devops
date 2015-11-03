# Supervisor Notes

## supervisord

The server piece of supervisor is named supervisord. It is responsible for starting child programs at its own invocation, responding to commands from clients, restarting crashed or exited subprocesseses, logging its subprocess stdout and stderr output, and generating and handling “events” corresponding to points in subprocess lifetimes.

## /etc/supervisord.conf

The server process uses a configuration file. This is typically located in /etc/supervisord.conf. This configuration file is an “Windows-INI” style config file. It is important to keep this file secure via proper filesystem permissions because it may contain unencrypted usernames and passwords. Use echo_supervisord_conf to generate a sample config file.

## supervisorctl

The command-line client piece of the supervisor is named supervisorctl. It provides a shell-like interface to the features provided by supervisord. From supervisorctl, a user can connect to different supervisord processes, get status on the subprocesses controlled by, stop and start subprocesses of, and get lists of running processes of a supervisord. It should be password protected.

## Web Server

A web user interface with functionality comparable to supervisorctl may be accessed via a browser if you start supervisord against an internet socket. Visit the server URL (e.g. http://localhost:9001/) to view and control process status through the web interface after activating the configuration file’s [inet_http_server] section.

* Introduction: http://supervisord.org/introduction.html
* Program settings: http://supervisord.org/configuration.html#program-x-section-settings
* Init Scripts: https://github.com/Supervisor/initscripts
* Generate supervisord conf: echo_supervisord_conf
*
