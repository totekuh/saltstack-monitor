# saltstack-monitor
This project is based on the saltstack automation framework. See https://www.saltstack.com/ for more info.

Saltstack WebMonitor is used for the three purposes:
<br/>1. Communicate with a WebMonitorMinion and ask him to collect information about web server's logs.
<br/>2. Receive this information, analyze it and print a report about suspicious traffic received by the web server.
<br/>3. According to the printed report, push generated iptables drop statements to the minion.

<b><h2>Installation</h2></b>
 
 
 <br/> On the <b>minion</b> side:
  <br/>1. install saltstack: run saltstack-minion-setup.sh from the project repo
  <br/>2. add a master's IP address to the salt-minion configuration file: /etc/salt/minion
<br/><br/> On the <b>master</b> side:
  <br/> 1. install saltstack: run saltstack-master-setup.sh from the project repo
  <br/> 2. minion will try to communicate with master since he is online. you should accept his key and authorize him.
  <br/> # salt-key --list
  <br/> # salt-key --accept <i>minion_id</i>

You can (and probably should) review the generated statements before pushing them, you also can receive a geolocation lookup about collected threats. You can run the WebMonitor in daemon mode to keep watching your WebMonitorMinion(s).

<br/> use ./web_monitor.py --help to get more info how to run it.
