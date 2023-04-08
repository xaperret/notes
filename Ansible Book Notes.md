---
annotation-target: Books/learn_ansible_quickly.pdf
date created: Tuesday, February 7th 2023, 9:37:15 am
date modified: Tuesday, February 7th 2023, 9:37:29 am
---


>%%
>```annotation-json
>{"created":"2023-03-28T08:18:46.611Z","updated":"2023-03-28T08:18:46.611Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":15277,"end":15477},{"type":"TextQuoteSelector","exact":"Ansible is an open-source configuration management, software provisioning, andapplication deployment tool that makes automating your application deploymentsand IT infrastructure operation very simple.","prefix":"ntOS,and Ubuntu.What is Ansible?","suffix":"Ansible is very lightweight, eas"}]}]}
>```
>%%
>*%%PREFIX%%ntOS,and Ubuntu.What is Ansible?%%HIGHLIGHT%% ==Ansible is an open-source configuration management, software provisioning, andapplication deployment tool that makes automating your application deploymentsand IT infrastructure operation very simple.== %%POSTFIX%%Ansible is very lightweight, eas*
>%%LINK%%[[#^e05pvpwu1sb|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^e05pvpwu1sb


>%%
>```annotation-json
>{"created":"2023-03-28T08:20:51.846Z","text":"Adhoc commands are a way to use ansible without having to create a playbook. It's not recommended to use root access for security reason. The best way is to set up a dedicated Ansible user with sudo privileges (to all commands) on all hosts (control and managed hosts).","updated":"2023-03-28T08:20:51.846Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":23543,"end":23923},{"type":"TextQuoteSelector","exact":"Even though you can use the root user in Ansible to run Ad-Hoc commands andplaybooks, it’s definitely not recommended and is not considered best practice dueto the security risks that can arise by allowing root user ssh access.For this reason, it’s recommended that you create a dedicated Ansible user withsudo privileges (to all commands) on all hosts (control and managed hosts)","prefix":"ommands.Creating an Ansible user","suffix":".Remember, Ansible uses SSH and "}]}]}
>```
>%%
>*%%PREFIX%%ommands.Creating an Ansible user%%HIGHLIGHT%% ==Even though you can use the root user in Ansible to run Ad-Hoc commands andplaybooks, it’s definitely not recommended and is not considered best practice dueto the security risks that can arise by allowing root user ssh access.For this reason, it’s recommended that you create a dedicated Ansible user withsudo privileges (to all commands) on all hosts (control and managed hosts)== %%POSTFIX%%.Remember, Ansible uses SSH and*
>%%LINK%%[[#^b8wssev3xjg|show annotation]]
>%%COMMENT%%
>Adhoc commands are a way to use ansible without having to create a playbook. It's not recommended to use root access for security reason. The best way is to set up a dedicated Ansible user with sudo privileges (to all commands) on all hosts (control and managed hosts).
>%%TAGS%%
>
^b8wssev3xjg


>%%
>```annotation-json
>{"created":"2023-03-28T08:23:15.141Z","updated":"2023-03-28T08:23:15.141Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":26234,"end":26429},{"type":"TextQuoteSelector","exact":"An Ansible inventory file is a basically a file that contains a list of servers, groupof servers, or ip addresses that references that hosts that you want to be managedby Ansible (managed nodes).","prefix":"9Building your Ansible inventory","suffix":"The /etc/ansible/hosts is the de"}]}]}
>```
>%%
>*%%PREFIX%%9Building your Ansible inventory%%HIGHLIGHT%% ==An Ansible inventory file is a basically a file that contains a list of servers, groupof servers, or ip addresses that references that hosts that you want to be managedby Ansible (managed nodes).== %%POSTFIX%%The /etc/ansible/hosts is the de*
>%%LINK%%[[#^1gv8qcrak8l|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^1gv8qcrak8l


>%%
>```annotation-json
>{"created":"2023-03-28T08:37:05.230Z","text":"Once you have created an inventory file. It's possible to class variables into groups and subgroups\n","updated":"2023-03-28T08:37:05.230Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":28149,"end":28211},{"type":"TextQuoteSelector","exact":"You can organize your managed hosts into groups and subgroups.","prefix":"eating host groups and subgroups","suffix":" For example, youcan edit the my"}]}]}
>```
>%%
>*%%PREFIX%%eating host groups and subgroups%%HIGHLIGHT%% ==You can organize your managed hosts into groups and subgroups.== %%POSTFIX%%For example, youcan edit the my*
>%%LINK%%[[#^ejmicqqy078|show annotation]]
>%%COMMENT%%
>Once you have created an inventory file. It's possible to class variables into groups and subgroups
>
>%%TAGS%%
>
^ejmicqqy078


>%%
>```annotation-json
>{"created":"2023-03-28T09:16:23.410Z","updated":"2023-03-28T09:16:23.410Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":33055,"end":33278},{"type":"TextQuoteSelector","exact":"An Ansible ad-hoc command is a great tool that you can use to run a single taskon one or more managed nodes. A typical Ansible ad-hoc command follows thegeneral syntax:ansible host_pattern -m module_name -a ”module_options”","prefix":"sible. Now, the real fun begins!","suffix":"The easiest way to understand ho"}]}]}
>```
>%%
>*%%PREFIX%%sible. Now, the real fun begins!%%HIGHLIGHT%% ==An Ansible ad-hoc command is a great tool that you can use to run a single taskon one or more managed nodes. A typical Ansible ad-hoc command follows thegeneral syntax:ansible host_pattern -m module_name -a ”module_options”== %%POSTFIX%%The easiest way to understand ho*
>%%LINK%%[[#^9d35pn9io0c|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^9d35pn9io0c


>%%
>```annotation-json
>{"created":"2023-03-28T09:29:53.255Z","updated":"2023-03-28T09:29:53.255Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":30889,"end":31205},{"type":"TextQuoteSelector","exact":"The /etc/ansible/ansible.cfg contains a whole of various Ansible configurationsettings and sections:[elliot@control plays]$ wc -l /etc/ansible/ansible.cfg490 /etc/ansible/ansible.cfgThe two most important sections that you need to define in your Ansible configu-ration file are:1. [defaults]2. [privilege_escalation]","prefix":"g file in the project directory.","suffix":"In the [defaults] section, here "}]}]}
>```
>%%
>*%%PREFIX%%g file in the project directory.%%HIGHLIGHT%% ==The /etc/ansible/ansible.cfg contains a whole of various Ansible configurationsettings and sections:[elliot@control plays]$ wc -l /etc/ansible/ansible.cfg490 /etc/ansible/ansible.cfgThe two most important sections that you need to define in your Ansible configu-ration file are:1. [defaults]2. [privilege_escalation]== %%POSTFIX%%In the [defaults] section, here*
>%%LINK%%[[#^dyv8jmmj8d6|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^dyv8jmmj8d6


>%%
>```annotation-json
>{"created":"2023-03-28T09:31:07.825Z","updated":"2023-03-28T09:31:07.825Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":33055,"end":33278},{"type":"TextQuoteSelector","exact":"An Ansible ad-hoc command is a great tool that you can use to run a single taskon one or more managed nodes. A typical Ansible ad-hoc command follows thegeneral syntax:ansible host_pattern -m module_name -a ”module_options”","prefix":"sible. Now, the real fun begins!","suffix":"The easiest way to understand ho"}]}]}
>```
>%%
>*%%PREFIX%%sible. Now, the real fun begins!%%HIGHLIGHT%% ==An Ansible ad-hoc command is a great tool that you can use to run a single taskon one or more managed nodes. A typical Ansible ad-hoc command follows thegeneral syntax:ansible host_pattern -m module_name -a ”module_options”== %%POSTFIX%%The easiest way to understand ho*
>%%LINK%%[[#^83o6y0x7z4l|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^83o6y0x7z4l


>%%
>```annotation-json
>{"created":"2023-03-28T09:33:40.855Z","updated":"2023-03-28T09:33:40.855Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":36730,"end":36839},{"type":"TextQuoteSelector","exact":"There are three Ansible modules that people often confuse with one another; theseare:1. command2. shell3. raw","prefix":"ommand vs. Shell vs. Raw Modules","suffix":"Those three modules achieve the "}]}]}
>```
>%%
>*%%PREFIX%%ommand vs. Shell vs. Raw Modules%%HIGHLIGHT%% ==There are three Ansible modules that people often confuse with one another; theseare:1. command2. shell3. raw== %%POSTFIX%%Those three modules achieve the*
>%%LINK%%[[#^gfpprf594u7|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^gfpprf594u7


>%%
>```annotation-json
>{"created":"2023-03-28T09:33:51.581Z","updated":"2023-03-28T09:33:51.581Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":37298,"end":37518},{"type":"TextQuoteSelector","exact":"That’s because the command module doesn’t support pipes or redirection. Youcan use the shell module instead if you want to use pipes or redirection. Run thesame command again, but this time, use the shell module instead:","prefix":"information.non-zero return code","suffix":"[elliot@control plays]$ ansible "}]}]}
>```
>%%
>*%%PREFIX%%information.non-zero return code%%HIGHLIGHT%% ==That’s because the command module doesn’t support pipes or redirection. Youcan use the shell module instead if you want to use pipes or redirection. Run thesame command again, but this time, use the shell module instead:== %%POSTFIX%%[elliot@control plays]$ ansible*
>%%LINK%%[[#^ft25gi9o9|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^ft25gi9o9


>%%
>```annotation-json
>{"created":"2023-03-28T09:40:19.979Z","updated":"2023-03-28T09:40:19.979Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":37898,"end":38298},{"type":"TextQuoteSelector","exact":"Now,the raw module just uses SSH and bypasses the Ansible module subsystem. Thisway, the raw module would successfully work on the managed node even if pythonis not installed (on the managed node).I tampered with my python binaries on node4 (please don’t do that yourself) so Ican mimic a scenario of what will happen if you run the shell or command moduleon a node that doesn’t have python installed","prefix":"the scenes to do all the magic. ","suffix":":20root@node4:/usr/bin# mkdir hi"}]}]}
>```
>%%
>*%%PREFIX%%the scenes to do all the magic.%%HIGHLIGHT%% ==Now,the raw module just uses SSH and bypasses the Ansible module subsystem. Thisway, the raw module would successfully work on the managed node even if pythonis not installed (on the managed node).I tampered with my python binaries on node4 (please don’t do that yourself) so Ican mimic a scenario of what will happen if you run the shell or command moduleon a node that doesn’t have python installed== %%POSTFIX%%:20root@node4:/usr/bin# mkdir hi*
>%%LINK%%[[#^rrj36yhnms|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^rrj36yhnms


>%%
>```annotation-json
>{"created":"2023-03-28T09:41:10.053Z","updated":"2023-03-28T09:41:10.053Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":39987,"end":40053},{"type":"TextQuoteSelector","exact":"Figure 7 summarizes the different use cases for the three modules:","prefix":"oot@node4:/usr/bin/hide# mv * ..","suffix":"Figure 7: command vs. shell vs. "}]}]}
>```
>%%
>*%%PREFIX%%oot@node4:/usr/bin/hide# mv * ..%%HIGHLIGHT%% ==Figure 7 summarizes the different use cases for the three modules:== %%POSTFIX%%Figure 7: command vs. shell vs.*
>%%LINK%%[[#^ljpcwj3n9|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^ljpcwj3n9


>%%
>```annotation-json
>{"created":"2023-03-28T09:46:30.323Z","updated":"2023-03-28T09:46:30.323Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":40958,"end":41138},{"type":"TextQuoteSelector","exact":"To better understand the differences between Ansible ad-hoc command and Ansi-ble playbooks; you can think of Ansible ad-hoc commands as Linux commands andplaybooks as bash scripts.","prefix":"g and running Ansible playbooks.","suffix":"Ansible ad-hoc commands are idea"}]}]}
>```
>%%
>*%%PREFIX%%g and running Ansible playbooks.%%HIGHLIGHT%% ==To better understand the differences between Ansible ad-hoc command and Ansi-ble playbooks; you can think of Ansible ad-hoc commands as Linux commands andplaybooks as bash scripts.== %%POSTFIX%%Ansible ad-hoc commands are idea*
>%%LINK%%[[#^054skqpqzohj|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^054skqpqzohj


>%%
>```annotation-json
>{"created":"2023-04-07T09:55:39.662Z","updated":"2023-04-07T09:55:39.662Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":41138,"end":41290},{"type":"TextQuoteSelector","exact":"Ansible ad-hoc commands are ideal to perform tasks that are not executed fre-quently such us getting servers uptime, retrieving system information, etc.","prefix":"ds andplaybooks as bash scripts.","suffix":" ]]On the other hand, Ansible pl"}]}]}
>```
>%%
>*%%PREFIX%%ds andplaybooks as bash scripts.%%HIGHLIGHT%% ==Ansible ad-hoc commands are ideal to perform tasks that are not executed fre-quently such us getting servers uptime, retrieving system information, etc.== %%POSTFIX%%]]On the other hand, Ansible pl*
>%%LINK%%[[#^cwajoyd3l6|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^cwajoyd3l6


>%%
>```annotation-json
>{"created":"2023-04-07T09:55:46.276Z","updated":"2023-04-07T09:55:46.276Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":41313,"end":41458},{"type":"TextQuoteSelector","exact":"nsible playbooks are ideal to automate complex tasks like sys-tem patches, application deployments, firewall configurations, user management,etc.","prefix":"ion, etc. ]]On the other hand, A","suffix":"Please note that I have included"}]}]}
>```
>%%
>*%%PREFIX%%ion, etc. ]]On the other hand, A%%HIGHLIGHT%% ==nsible playbooks are ideal to automate complex tasks like sys-tem patches, application deployments, firewall configurations, user management,etc.== %%POSTFIX%%Please note that I have included*
>%%LINK%%[[#^2lmuent82im|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^2lmuent82im


>%%
>```annotation-json
>{"created":"2023-04-07T09:55:59.637Z","updated":"2023-04-07T09:55:59.637Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":41635,"end":41702},{"type":"TextQuoteSelector","exact":"Playbooks are written in YAML (Yet Another Markup Language) format.","prefix":"ting your first Ansible playbook","suffix":" If youdon’t know YAML; I have i"}]}]}
>```
>%%
>*%%PREFIX%%ting your first Ansible playbook%%HIGHLIGHT%% ==Playbooks are written in YAML (Yet Another Markup Language) format.== %%POSTFIX%%If youdon’t know YAML; I have i*
>%%LINK%%[[#^ok7ag0ak2mg|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^ok7ag0ak2mg


>%%
>```annotation-json
>{"created":"2023-04-07T10:00:47.814Z","updated":"2023-04-07T10:00:47.814Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":42029,"end":42229},{"type":"TextQuoteSelector","exact":"Also, YAML is indentation sensitive. A two-spaces indentation is the recommendedindentation to use in YAML; however, YAML will follow whatever indentationsystem a file uses as long as it’s consistent.","prefix":"’s less typing, and I am lazy.24","suffix":"It is beyond annoying to keep hi"}]}]}
>```
>%%
>*%%PREFIX%%’s less typing, and I am lazy.24%%HIGHLIGHT%% ==Also, YAML is indentation sensitive. A two-spaces indentation is the recommendedindentation to use in YAML; however, YAML will follow whatever indentationsystem a file uses as long as it’s consistent.== %%POSTFIX%%It is beyond annoying to keep hi*
>%%LINK%%[[#^qar07gbjts|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^qar07gbjts
