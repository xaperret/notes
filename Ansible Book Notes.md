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


>%%
>```annotation-json
>{"created":"2023-04-09T09:49:52.947Z","updated":"2023-04-09T09:49:52.947Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":47969,"end":48051},{"type":"TextQuoteSelector","exact":"You can use the --syntax-check option to check if your playbook has syntax errors:","prefix":"ook is free of potential errors.","suffix":"[elliot@control plays]$ ansible-"}]}]}
>```
>%%
>*%%PREFIX%%ook is free of potential errors.%%HIGHLIGHT%% ==You can use the --syntax-check option to check if your playbook has syntax errors:== %%POSTFIX%%[elliot@control plays]$ ansible-*
>%%LINK%%[[#^vdpmiwifhe|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^vdpmiwifhe


>%%
>```annotation-json
>{"created":"2023-04-09T09:50:01.235Z","updated":"2023-04-09T09:50:01.235Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":48153,"end":48266},{"type":"TextQuoteSelector","exact":"You may also want to use the --check option to do a dry run of your playbookbefore actually running the playbook:","prefix":".ymlplaybook: first-playbook.yml","suffix":"[elliot@control plays]$ ansible-"}]}]}
>```
>%%
>*%%PREFIX%%.ymlplaybook: first-playbook.yml%%HIGHLIGHT%% ==You may also want to use the --check option to do a dry run of your playbookbefore actually running the playbook:== %%POSTFIX%%[elliot@control plays]$ ansible-*
>%%LINK%%[[#^ty23jwwsdz9|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^ty23jwwsdz9


>%%
>```annotation-json
>{"created":"2023-04-09T09:51:35.568Z","updated":"2023-04-09T09:51:35.568Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":50167,"end":50279},{"type":"TextQuoteSelector","exact":"Now you can use the import_tasks module to run all the tasks in group-tasks.ymlin your first playbook as follows","prefix":"finance groupgroup:name: finance","suffix":":[elliot@control plays]$ cat fir"}]}]}
>```
>%%
>*%%PREFIX%%finance groupgroup:name: finance%%HIGHLIGHT%% ==Now you can use the import_tasks module to run all the tasks in group-tasks.ymlin your first playbook as follows== %%POSTFIX%%:[elliot@control plays]$ cat fir*
>%%LINK%%[[#^017o6kkbejftl|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^017o6kkbejftl


>%%
>```annotation-json
>{"created":"2023-04-09T09:51:45.400Z","updated":"2023-04-09T09:51:45.400Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":50497,"end":50666},{"type":"TextQuoteSelector","exact":"You can also use the import_playbook module to reuse an entire playbook. Forexample, you can create a new playbook named reuse-playbook.yml that has thefollowing content","prefix":"upsimport_tasks: group-tasks.yml","suffix":":[elliot@control plays]$ cat reu"}]}]}
>```
>%%
>*%%PREFIX%%upsimport_tasks: group-tasks.yml%%HIGHLIGHT%% ==You can also use the import_playbook module to reuse an entire playbook. Forexample, you can create a new playbook named reuse-playbook.yml that has thefollowing content== %%POSTFIX%%:[elliot@control plays]$ cat reu*
>%%LINK%%[[#^zc40x35ej88|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^zc40x35ej88


>%%
>```annotation-json
>{"created":"2023-04-09T09:54:41.860Z","updated":"2023-04-09T09:54:41.860Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":51367,"end":51637},{"type":"TextQuoteSelector","exact":"The only difference is that the import statements are pre-processed at the timeplaybooks are parsed. On the other hand, include statements are processed as theyare encountered during the execution of the playbook. So, in summary, import isstatic while include is dynamic","prefix":"ybookinclude: first-playbook.yml","suffix":".33Running selective tasks and p"}]}]}
>```
>%%
>*%%PREFIX%%ybookinclude: first-playbook.yml%%HIGHLIGHT%% ==The only difference is that the import statements are pre-processed at the timeplaybooks are parsed. On the other hand, include statements are processed as theyare encountered during the execution of the playbook. So, in summary, import isstatic while include is dynamic== %%POSTFIX%%.33Running selective tasks and p*
>%%LINK%%[[#^xpa5az3ifpj|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^xpa5az3ifpj


>%%
>```annotation-json
>{"created":"2023-04-09T09:56:06.038Z","updated":"2023-04-09T09:56:06.038Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":51673,"end":51814},{"type":"TextQuoteSelector","exact":"You can choose not to run a whole playbook and instead may want to run specifictask(s) or play(s) in a playbook. To do this, you can use tags","prefix":"unning selective tasks and plays","suffix":".For example, you can tag the in"}]}]}
>```
>%%
>*%%PREFIX%%unning selective tasks and plays%%HIGHLIGHT%% ==You can choose not to run a whole playbook and instead may want to run specifictask(s) or play(s) in a playbook. To do this, you can use tags== %%POSTFIX%%.For example, you can tag the in*
>%%LINK%%[[#^5pqg6b8g83i|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^5pqg6b8g83i


>%%
>```annotation-json
>{"created":"2023-04-09T09:56:32.590Z","updated":"2023-04-09T09:56:32.590Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":52212,"end":52307},{"type":"TextQuoteSelector","exact":"Now you can use the --tags option followed by the tag name git to only run theinstall git task:","prefix":"name: gitstate: presenttags: git","suffix":"[elliot@control plays]$ ansible-"}]}]}
>```
>%%
>*%%PREFIX%%name: gitstate: presenttags: git%%HIGHLIGHT%% ==Now you can use the --tags option followed by the tag name git to only run theinstall git task:== %%POSTFIX%%[elliot@control plays]$ ansible-*
>%%LINK%%[[#^2s3rw4hxx4p|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^2s3rw4hxx4p


>%%
>```annotation-json
>{"created":"2023-04-09T10:05:54.216Z","updated":"2023-04-09T10:05:54.216Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":53893,"end":53969},{"type":"TextQuoteSelector","exact":"You can use the vars keyword to define variables directly inside a playbook.","prefix":"fining and referencing variables","suffix":"For example, you can define a fa"}]}]}
>```
>%%
>*%%PREFIX%%fining and referencing variables%%HIGHLIGHT%% ==You can use the vars keyword to define variables directly inside a playbook.== %%POSTFIX%%For example, you can define a fa*
>%%LINK%%[[#^k49ntoql0u|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^k49ntoql0u


>%%
>```annotation-json
>{"created":"2023-04-09T10:16:08.023Z","updated":"2023-04-09T10:16:08.023Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":54338,"end":54444},{"type":"TextQuoteSelector","exact":"To get the value of the fav_color variable; you need to surround it by a pair ofcurly brackets as follows:","prefix":"st need to know the very basics.","suffix":"My favorite color is {{ fav_colo"}]}]}
>```
>%%
>*%%PREFIX%%st need to know the very basics.%%HIGHLIGHT%% ==To get the value of the fav_color variable; you need to surround it by a pair ofcurly brackets as follows:== %%POSTFIX%%My favorite color is {{ fav_colo*
>%%LINK%%[[#^z9j5mw4vieb|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^z9j5mw4vieb


>%%
>```annotation-json
>{"created":"2023-04-09T10:16:20.829Z","updated":"2023-04-09T10:16:20.829Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":54176,"end":54240},{"type":"TextQuoteSelector","exact":"Ansible uses the Jinja2templating system to work with variables.","prefix":"erence) the fav_color variable? ","suffix":" You will learn all about Jinja2"}]}]}
>```
>%%
>*%%PREFIX%%erence) the fav_color variable?%%HIGHLIGHT%% ==Ansible uses the Jinja2templating system to work with variables.== %%POSTFIX%%You will learn all about Jinja2*
>%%LINK%%[[#^kgsmp1fff1m|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^kgsmp1fff1m


>%%
>```annotation-json
>{"created":"2023-04-09T10:17:12.881Z","updated":"2023-04-09T10:17:12.881Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":55478,"end":55549},{"type":"TextQuoteSelector","exact":"You can also use lists and dictionaries to define multivalued variables","prefix":"0Creating lists and dictionaries","suffix":". For example,you may define a l"}]}]}
>```
>%%
>*%%PREFIX%%0Creating lists and dictionaries%%HIGHLIGHT%% ==You can also use lists and dictionaries to define multivalued variables== %%POSTFIX%%. For example,you may define a l*
>%%LINK%%[[#^7jsrkjics52|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^7jsrkjics52


>%%
>```annotation-json
>{"created":"2023-04-09T10:17:35.757Z","updated":"2023-04-09T10:17:35.757Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":55792,"end":55844},{"type":"TextQuoteSelector","exact":"You can print all the values in port_nums as follows","prefix":"t_nums:- 21- 22- 23- 25- 80- 443","suffix":":All the ports {{ port_nums }}Yo"}]}]}
>```
>%%
>*%%PREFIX%%t_nums:- 21- 22- 23- 25- 80- 443%%HIGHLIGHT%% ==You can print all the values in port_nums as follows== %%POSTFIX%%:All the ports {{ port_nums }}Yo*
>%%LINK%%[[#^qkhgjgp6p4l|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^qkhgjgp6p4l


>%%
>```annotation-json
>{"created":"2023-04-09T10:17:45.726Z","updated":"2023-04-09T10:17:45.726Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":55874,"end":55918},{"type":"TextQuoteSelector","exact":"You can also access a specific list element:","prefix":"ws:All the ports {{ port_nums }}","suffix":"First port is {{ port_nums[0] }}"}]}]}
>```
>%%
>*%%PREFIX%%ws:All the ports {{ port_nums }}%%HIGHLIGHT%% ==You can also access a specific list element:== %%POSTFIX%%First port is {{ port_nums[0] }}*
>%%LINK%%[[#^chfq49br5m|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^chfq49br5m


>%%
>```annotation-json
>{"created":"2023-04-09T10:22:58.830Z","updated":"2023-04-09T10:22:58.830Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":56014,"end":56070},{"type":"TextQuoteSelector","exact":"You can also define a dictionary named users as follows:","prefix":"sition) to access list elements.","suffix":"vars:users:bob:username: bobuid:"}]}]}
>```
>%%
>*%%PREFIX%%sition) to access list elements.%%HIGHLIGHT%% ==You can also define a dictionary named users as follows:== %%POSTFIX%%vars:users:bob:username: bobuid:*
>%%LINK%%[[#^3sifxy5u4lc|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^3sifxy5u4lc


>%%
>```annotation-json
>{"created":"2023-04-09T10:23:14.122Z","updated":"2023-04-09T10:23:14.122Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":56165,"end":56235},{"type":"TextQuoteSelector","exact":"There are two different ways you can use to access dictionary elements","prefix":"ame: lisauid: 2233shell: /bin/sh","suffix":":• dict_name[’key’] → users[’bob"}]}]}
>```
>%%
>*%%PREFIX%%ame: lisauid: 2233shell: /bin/sh%%HIGHLIGHT%% ==There are two different ways you can use to access dictionary elements== %%POSTFIX%%:• dict_name[’key’] → users[’bob*
>%%LINK%%[[#^8fhqpw48ax6|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^8fhqpw48ax6


>%%
>```annotation-json
>{"created":"2023-04-09T11:54:22.210Z","updated":"2023-04-09T11:54:22.210Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":57240,"end":57426},{"type":"TextQuoteSelector","exact":"Just like you can import (or include) tasks in a playbook. You can do the samething with variables as well. That is, in a playbook, you can include variables de-fined in an external file","prefix":"\"}40Including external variables","suffix":".To demonstrate, let’s create a "}]}]}
>```
>%%
>*%%PREFIX%%"}40Including external variables%%HIGHLIGHT%% ==Just like you can import (or include) tasks in a playbook. You can do the samething with variables as well. That is, in a playbook, you can include variables de-fined in an external file== %%POSTFIX%%.To demonstrate, let’s create a*
>%%LINK%%[[#^1l2edxxf74w|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^1l2edxxf74w


>%%
>```annotation-json
>{"created":"2023-04-09T11:56:49.601Z","updated":"2023-04-09T11:56:49.601Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":58521,"end":58612},{"type":"TextQuoteSelector","exact":"You can use the vars_prompt keyword to prompt the user to set a variable’s valueat runtime.","prefix":"ort_nums[1] }}Getting user input","suffix":"For example, the following greet"}]}]}
>```
>%%
>*%%PREFIX%%ort_nums[1] }}Getting user input%%HIGHLIGHT%% ==You can use the vars_prompt keyword to prompt the user to set a variable’s valueat runtime.== %%POSTFIX%%For example, the following greet*
>%%LINK%%[[#^w3wbe62lv7d|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^w3wbe62lv7d


>%%
>```annotation-json
>{"created":"2023-04-09T12:01:00.560Z","updated":"2023-04-09T12:01:00.560Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":59330,"end":59520},{"type":"TextQuoteSelector","exact":"You can set variables that are specific to your managed hosts. By doing so, you cancreate much more eﬀicient playbooks as you don’t need to write repeated tasks fordifferent nodes or groups.","prefix":"Setting host and group variables","suffix":"To demonstrate, edit your invent"}]}]}
>```
>%%
>*%%PREFIX%%Setting host and group variables%%HIGHLIGHT%% ==You can set variables that are specific to your managed hosts. By doing so, you cancreate much more eﬀicient playbooks as you don’t need to write repeated tasks fordifferent nodes or groups.== %%POSTFIX%%To demonstrate, edit your invent*
>%%LINK%%[[#^wws289t8z6a|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^wws289t8z6a


>%%
>```annotation-json
>{"created":"2023-04-09T12:04:08.221Z","updated":"2023-04-09T12:04:08.221Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":61735,"end":61824},{"type":"TextQuoteSelector","exact":"If the same variable is set at different levels; the most specific level gets precedence.","prefix":"at different scopes (or levels).","suffix":"For example, a variable that is "}]}]}
>```
>%%
>*%%PREFIX%%at different scopes (or levels).%%HIGHLIGHT%% ==If the same variable is set at different levels; the most specific level gets precedence.== %%POSTFIX%%For example, a variable that is*
>%%LINK%%[[#^vzxcl7s2qzp|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^vzxcl7s2qzp


>%%
>```annotation-json
>{"created":"2023-04-09T12:04:16.380Z","updated":"2023-04-09T12:04:16.380Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":61824,"end":61946},{"type":"TextQuoteSelector","exact":"For example, a variable that is set on a play level takes precedence over the samevariable set on a host level (host_vars)","prefix":" specific level gets precedence.","suffix":".44Furthermore, a variable that "}]}]}
>```
>%%
>*%%PREFIX%%specific level gets precedence.%%HIGHLIGHT%% ==For example, a variable that is set on a play level takes precedence over the samevariable set on a host level (host_vars)== %%POSTFIX%%.44Furthermore, a variable that*
>%%LINK%%[[#^xx2n2l81trm|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^xx2n2l81trm


>%%
>```annotation-json
>{"created":"2023-04-09T12:04:30.593Z","updated":"2023-04-09T12:04:30.593Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":61949,"end":62097},{"type":"TextQuoteSelector","exact":"Furthermore, a variable that is set on the command line using the --extra-varstakes the highest precedence, that is, it will overwrite anything else","prefix":"t on a host level (host_vars).44","suffix":".To demonstrate, let’s create a "}]}]}
>```
>%%
>*%%PREFIX%%t on a host level (host_vars).44%%HIGHLIGHT%% ==Furthermore, a variable that is set on the command line using the --extra-varstakes the highest precedence, that is, it will overwrite anything else== %%POSTFIX%%.To demonstrate, let’s create a*
>%%LINK%%[[#^sse8av851w|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^sse8av851w


>%%
>```annotation-json
>{"created":"2023-04-09T12:04:54.889Z","updated":"2023-04-09T12:04:54.889Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":63004,"end":63180},{"type":"TextQuoteSelector","exact":"You can retrieve or discover variables that contain information about your managedhosts. These variables are called facts and Ansible uses the setup module to gatherthese facts","prefix":"u”.45Gathering and showing facts","suffix":". The IP address on one of your "}]}]}
>```
>%%
>*%%PREFIX%%u”.45Gathering and showing facts%%HIGHLIGHT%% ==You can retrieve or discover variables that contain information about your managedhosts. These variables are called facts and Ansible uses the setup module to gatherthese facts== %%POSTFIX%%. The IP address on one of your*
>%%LINK%%[[#^bbqeoielbz6|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^bbqeoielbz6


>%%
>```annotation-json
>{"created":"2023-04-09T12:11:40.926Z","updated":"2023-04-09T12:11:40.926Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":64188,"end":64296},{"type":"TextQuoteSelector","exact":"Notice how the facts are stored in dictionaries or listsand they all belong to the ansible_facts dictionary.","prefix":" seedisplayed on your terminal. ","suffix":"By default, the setup module is "}]}]}
>```
>%%
>*%%PREFIX%%seedisplayed on your terminal.%%HIGHLIGHT%% ==Notice how the facts are stored in dictionaries or listsand they all belong to the ansible_facts dictionary.== %%POSTFIX%%By default, the setup module is*
>%%LINK%%[[#^nv82zt61eak|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^nv82zt61eak


>%%
>```annotation-json
>{"created":"2023-04-09T12:11:50.216Z","updated":"2023-04-09T12:11:50.216Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":64749,"end":64858},{"type":"TextQuoteSelector","exact":"You can turn off facts gathering by setting gather_facts boolean to false right inyour play header as follows","prefix":"[node3]ok: [node2]ok: [node1]...","suffix":":[elliot@control plays]$ cat mot"}]}]}
>```
>%%
>*%%PREFIX%%[node3]ok: [node2]ok: [node1]...%%HIGHLIGHT%% ==You can turn off facts gathering by setting gather_facts boolean to false right inyour play header as follows== %%POSTFIX%%:[elliot@control plays]$ cat mot*
>%%LINK%%[[#^yurlxudabe|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^yurlxudabe


>%%
>```annotation-json
>{"created":"2023-04-09T12:13:16.783Z","updated":"2023-04-09T12:13:16.783Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":65280,"end":65440},{"type":"TextQuoteSelector","exact":"The same way you show a variable’s value; you can also use to show a fact’s value.The following show-facts.yml playbook displays the value of few facts on node1","prefix":"ge variable.] ******************","suffix":":[elliot@control plays]$ cat sho"}]}]}
>```
>%%
>*%%PREFIX%%ge variable.] ******************%%HIGHLIGHT%% ==The same way you show a variable’s value; you can also use to show a fact’s value.The following show-facts.yml playbook displays the value of few facts on node1== %%POSTFIX%%:[elliot@control plays]$ cat sho*
>%%LINK%%[[#^u25zxxto18|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^u25zxxto18


>%%
>```annotation-json
>{"created":"2023-04-09T12:14:09.506Z","updated":"2023-04-09T12:14:09.506Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":66337,"end":66539},{"type":"TextQuoteSelector","exact":"You may want to create your own custom facts. To do this, you can either use theset_fact module to add temporarily facts or the /etc/ansible/facts.d directoryto add permanent facts on your managed nodes","prefix":"kipped=048Creating customs facts","suffix":".I am going to show you how to a"}]}]}
>```
>%%
>*%%PREFIX%%kipped=048Creating customs facts%%HIGHLIGHT%% ==You may want to create your own custom facts. To do this, you can either use theset_fact module to add temporarily facts or the /etc/ansible/facts.d directoryto add permanent facts on your managed nodes== %%POSTFIX%%.I am going to show you how to a*
>%%LINK%%[[#^6i5foaiuwtm|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^6i5foaiuwtm


>%%
>```annotation-json
>{"created":"2023-04-09T12:17:28.448Z","updated":"2023-04-09T12:17:28.448Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":68691,"end":68884},{"type":"TextQuoteSelector","exact":"You can use a register to capture the output of a task and save it to a variable.This allows you to make use of a task output elsewhere in a playbook by simplyaddressing the registered variable","prefix":" output when running a playbook.","suffix":".The following register-playbook"}]}]}
>```
>%%
>*%%PREFIX%%output when running a playbook.%%HIGHLIGHT%% ==You can use a register to capture the output of a task and save it to a variable.This allows you to make use of a task output elsewhere in a playbook by simplyaddressing the registered variable== %%POSTFIX%%.The following register-playbook*
>%%LINK%%[[#^gn98v0l9guo|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^gn98v0l9guo


>%%
>```annotation-json
>{"created":"2023-04-09T12:19:15.969Z","updated":"2023-04-09T12:19:15.969Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":71757,"end":71948},{"type":"TextQuoteSelector","exact":"Ansible uses the loop keyword to iterate over the elements of a list. To demonstrate,let’s create a very simple playbook named print-list.yml that shows you how toprint the elements in a list","prefix":"nd over again.Looping over lists","suffix":":[elliot@control plays]$ cat pri"}]}]}
>```
>%%
>*%%PREFIX%%nd over again.Looping over lists%%HIGHLIGHT%% ==Ansible uses the loop keyword to iterate over the elements of a list. To demonstrate,let’s create a very simple playbook named print-list.yml that shows you how toprint the elements in a list== %%POSTFIX%%:[elliot@control plays]$ cat pri*
>%%LINK%%[[#^kb65qa9elvm|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^kb65qa9elvm


>%%
>```annotation-json
>{"created":"2023-04-09T12:25:46.921Z","updated":"2023-04-09T12:25:46.921Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":75182,"end":75207},{"type":"TextQuoteSelector","exact":"Looping over dictionaries","prefix":"03:1006::/home/jason:/bin/bash56","suffix":"You can only use loops with list"}]}]}
>```
>%%
>*%%PREFIX%%03:1006::/home/jason:/bin/bash56%%HIGHLIGHT%% ==Looping over dictionaries== %%POSTFIX%%You can only use loops with list*
>%%LINK%%[[#^sertnfaymr|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^sertnfaymr


>%%
>```annotation-json
>{"created":"2023-04-09T12:25:51.578Z","updated":"2023-04-09T12:25:51.578Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":71739,"end":71757},{"type":"TextQuoteSelector","exact":"Looping over lists","prefix":" whole task over and over again.","suffix":"Ansible uses the loop keyword to"}]}]}
>```
>%%
>*%%PREFIX%%whole task over and over again.%%HIGHLIGHT%% ==Looping over lists== %%POSTFIX%%Ansible uses the loop keyword to*
>%%LINK%%[[#^s2iwfpr2czr|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^s2iwfpr2czr


>%%
>```annotation-json
>{"created":"2023-04-09T12:28:07.255Z","updated":"2023-04-09T12:28:07.255Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":76265,"end":76402},{"type":"TextQuoteSelector","exact":"To fix this error; you can use the dict2items filter to convert a dictionary to a list.So, in the print-dict.yml playbook; edit the line:","prefix":"ly says that it requires a list.","suffix":"loop: \"{{ employee }}\"57and appl"}]}]}
>```
>%%
>*%%PREFIX%%ly says that it requires a list.%%HIGHLIGHT%% ==To fix this error; you can use the dict2items filter to convert a dictionary to a list.So, in the print-dict.yml playbook; edit the line:== %%POSTFIX%%loop: "{{ employee }}"57and appl*
>%%LINK%%[[#^58sksp5gbc2|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^58sksp5gbc2


>%%
>```annotation-json
>{"created":"2023-04-09T12:28:15.672Z","updated":"2023-04-09T12:28:15.672Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":76426,"end":76469},{"type":"TextQuoteSelector","exact":"and apply the dict2items filter as follows:","prefix":"he line:loop: \"{{ employee }}\"57","suffix":"loop: \"{{ employee | dict2items "}]}]}
>```
>%%
>*%%PREFIX%%he line:loop: "{{ employee }}"57%%HIGHLIGHT%% ==and apply the dict2items filter as follows:== %%POSTFIX%%loop: "{{ employee | dict2items*
>%%LINK%%[[#^gof2yr14wqq|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^gof2yr14wqq


>%%
>```annotation-json
>{"created":"2023-04-09T12:28:20.667Z","updated":"2023-04-09T12:28:20.667Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":77257,"end":77288},{"type":"TextQuoteSelector","exact":"Looping over a range of numbers","prefix":"yee dictionary were displayed.58","suffix":"You can use the range() function"}]}]}
>```
>%%
>*%%PREFIX%%yee dictionary were displayed.58%%HIGHLIGHT%% ==Looping over a range of numbers== %%POSTFIX%%You can use the range() function*
>%%LINK%%[[#^2f7y58eziwx|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^2f7y58eziwx


>%%
>```annotation-json
>{"created":"2023-04-09T12:29:41.758Z","updated":"2023-04-09T12:29:41.758Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":77288,"end":77379},{"type":"TextQuoteSelector","exact":"You can use the range() function along with the list filter to loop over a range ofnumbers.","prefix":"8Looping over a range of numbers","suffix":"For example, the following task "}]}]}
>```
>%%
>*%%PREFIX%%8Looping over a range of numbers%%HIGHLIGHT%% ==You can use the range() function along with the list filter to loop over a range ofnumbers.== %%POSTFIX%%For example, the following task*
>%%LINK%%[[#^y6alvf3nfh|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^y6alvf3nfh


>%%
>```annotation-json
>{"created":"2023-04-09T12:30:04.806Z","updated":"2023-04-09T12:30:04.806Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":78018,"end":78042},{"type":"TextQuoteSelector","exact":"Looping over inventories","prefix":"tart=0, end<256, and stride=2.59","suffix":"You can use the Ansible built-in"}]}]}
>```
>%%
>*%%PREFIX%%tart=0, end<256, and stride=2.59%%HIGHLIGHT%% ==Looping over inventories== %%POSTFIX%%You can use the Ansible built-in*
>%%LINK%%[[#^a8599gigu8e|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^a8599gigu8e


>%%
>```annotation-json
>{"created":"2023-04-09T12:30:38.569Z","updated":"2023-04-09T12:30:38.569Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":78042,"end":78215},{"type":"TextQuoteSelector","exact":"You can use the Ansible built-in groups variable to loop over all your inventoryhosts or just a subset of it. For instance, to loop over all your inventory hosts; youcan use","prefix":"ide=2.59Looping over inventories","suffix":":loop: \"{{ groups['all'] }}\"If y"}]}]}
>```
>%%
>*%%PREFIX%%ide=2.59Looping over inventories%%HIGHLIGHT%% ==You can use the Ansible built-in groups variable to loop over all your inventoryhosts or just a subset of it. For instance, to loop over all your inventory hosts; youcan use== %%POSTFIX%%:loop: "{{ groups['all'] }}"If y*
>%%LINK%%[[#^s511gonux78|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^s511gonux78


>%%
>```annotation-json
>{"created":"2023-04-09T12:30:51.813Z","updated":"2023-04-09T12:30:51.813Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":79230,"end":79250},{"type":"TextQuoteSelector","exact":"Pausing within loops","prefix":" able to ping(reach) each other.","suffix":"You may want to pause for a cert"}]}]}
>```
>%%
>*%%PREFIX%%able to ping(reach) each other.%%HIGHLIGHT%% ==Pausing within loops== %%POSTFIX%%You may want to pause for a cert*
>%%LINK%%[[#^vsiqusswix8|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^vsiqusswix8


>%%
>```annotation-json
>{"created":"2023-04-09T12:30:58.024Z","updated":"2023-04-09T12:30:58.024Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":79250,"end":79408},{"type":"TextQuoteSelector","exact":"You may want to pause for a certain amount of time between each loop iteration.To do this, you can use the pause directive along with the loop_control keyword","prefix":" each other.Pausing within loops","suffix":".To demonstrate, let’s create a "}]}]}
>```
>%%
>*%%PREFIX%%each other.Pausing within loops%%HIGHLIGHT%% ==You may want to pause for a certain amount of time between each loop iteration.To do this, you can use the pause directive along with the loop_control keyword== %%POSTFIX%%.To demonstrate, let’s create a*
>%%LINK%%[[#^39mcz7fl7wb|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^39mcz7fl7wb


>%%
>```annotation-json
>{"created":"2023-04-09T12:31:58.597Z","updated":"2023-04-09T12:31:58.597Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":81625,"end":81651},{"type":"TextQuoteSelector","exact":"Choosing When to Run Tasks","prefix":"rs to trigger tasks upon change.","suffix":"In this section, you will learn "}]}]}
>```
>%%
>*%%PREFIX%%rs to trigger tasks upon change.%%HIGHLIGHT%% ==Choosing When to Run Tasks== %%POSTFIX%%In this section, you will learn*
>%%LINK%%[[#^vcv34jfmbw|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^vcv34jfmbw


>%%
>```annotation-json
>{"created":"2023-04-09T12:32:01.257Z","updated":"2023-04-09T12:32:01.257Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":81755,"end":81776},{"type":"TextQuoteSelector","exact":"Using when with facts","prefix":"ertain taskin Ansible playbooks.","suffix":"You can use when conditional sta"}]}]}
>```
>%%
>*%%PREFIX%%ertain taskin Ansible playbooks.%%HIGHLIGHT%% ==Using when with facts== %%POSTFIX%%You can use when conditional sta*
>%%LINK%%[[#^6nvet42f7pc|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^6nvet42f7pc


>%%
>```annotation-json
>{"created":"2023-04-09T12:32:06.276Z","updated":"2023-04-09T12:32:06.276Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":81776,"end":81869},{"type":"TextQuoteSelector","exact":"You can use when conditional statements to run a task only when a certain condi-tion is true.","prefix":" playbooks.Using when with facts","suffix":" To demonstrate, create a new pl"}]}]}
>```
>%%
>*%%PREFIX%%playbooks.Using when with facts%%HIGHLIGHT%% ==You can use when conditional statements to run a task only when a certain condi-tion is true.== %%POSTFIX%%To demonstrate, create a new pl*
>%%LINK%%[[#^m76yvzja70d|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^m76yvzja70d


>%%
>```annotation-json
>{"created":"2023-04-09T12:32:56.766Z","updated":"2023-04-09T12:32:56.766Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":83190,"end":83215},{"type":"TextQuoteSelector","exact":"Using when with registers","prefix":"on node4 as itis running Ubuntu.","suffix":"You can also use when conditiona"}]}]}
>```
>%%
>*%%PREFIX%%on node4 as itis running Ubuntu.%%HIGHLIGHT%% ==Using when with registers== %%POSTFIX%%You can also use when conditiona*
>%%LINK%%[[#^wjq3lzjf6w|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^wjq3lzjf6w


>%%
>```annotation-json
>{"created":"2023-04-09T12:33:30.443Z","updated":"2023-04-09T12:33:30.443Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":84806,"end":84843},{"type":"TextQuoteSelector","exact":"Testing multiple conditions with when","prefix":"nodesand skipped node4 (Ubuntu).","suffix":"You can also test multiple condi"}]}]}
>```
>%%
>*%%PREFIX%%nodesand skipped node4 (Ubuntu).%%HIGHLIGHT%% ==Testing multiple conditions with when== %%POSTFIX%%You can also test multiple condi*
>%%LINK%%[[#^5i1e5gyvyur|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^5i1e5gyvyur


>%%
>```annotation-json
>{"created":"2023-04-09T12:33:59.092Z","updated":"2023-04-09T12:33:59.092Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":84994,"end":84997},{"type":"TextQuoteSelector","exact":"and","prefix":"8.yml playbook uses the logical ","suffix":" operatorto reboot servers that "}]}]}
>```
>%%
>*%%PREFIX%%8.yml playbook uses the logical%%HIGHLIGHT%% ==and== %%POSTFIX%%operatorto reboot servers that*
>%%LINK%%[[#^xxlr3b7hx8|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^xxlr3b7hx8


>%%
>```annotation-json
>{"created":"2023-04-09T12:34:02.457Z","updated":"2023-04-09T12:34:02.457Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":85346,"end":85348},{"type":"TextQuoteSelector","exact":"or","prefix":"\"8\"You can also use the logical ","suffix":" operator to run a task if any o"}]}]}
>```
>%%
>*%%PREFIX%%"8"You can also use the logical%%HIGHLIGHT%% ==or== %%POSTFIX%%operator to run a task if any o*
>%%LINK%%[[#^7387ga5d7cm|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^7387ga5d7cm


>%%
>```annotation-json
>{"created":"2023-04-09T12:34:05.945Z","updated":"2023-04-09T12:34:05.945Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":85673,"end":85694},{"type":"TextQuoteSelector","exact":"Using when with loops","prefix":"acts['distribution'] == \"RedHat\"","suffix":"If you combine a when conditiona"}]}]}
>```
>%%
>*%%PREFIX%%acts['distribution'] == "RedHat"%%HIGHLIGHT%% ==Using when with loops== %%POSTFIX%%If you combine a when conditiona*
>%%LINK%%[[#^5p2cj7renak|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^5p2cj7renak


>%%
>```annotation-json
>{"created":"2023-04-09T12:34:14.520Z","updated":"2023-04-09T12:34:14.520Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":85694,"end":85809},{"type":"TextQuoteSelector","exact":"If you combine a when conditional with a loop, Ansible would test the conditionfor each item in the loop separately","prefix":"== \"RedHat\"Using when with loops","suffix":".For example, the following prin"}]}]}
>```
>%%
>*%%PREFIX%%== "RedHat"Using when with loops%%HIGHLIGHT%% ==If you combine a when conditional with a loop, Ansible would test the conditionfor each item in the loop separately== %%POSTFIX%%.For example, the following prin*
>%%LINK%%[[#^8499mmmsf9t|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^8499mmmsf9t


>%%
>```annotation-json
>{"created":"2023-04-09T12:34:21.699Z","updated":"2023-04-09T12:34:21.699Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":86896,"end":86921},{"type":"TextQuoteSelector","exact":"Using when with variables","prefix":"unreachable=0 failed=0 skipped=0","suffix":"You can also use when conditiona"}]}]}
>```
>%%
>*%%PREFIX%%unreachable=0 failed=0 skipped=0%%HIGHLIGHT%% ==Using when with variables== %%POSTFIX%%You can also use when conditiona*
>%%LINK%%[[#^6ribrpydkcw|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^6ribrpydkcw


>%%
>```annotation-json
>{"created":"2023-04-09T12:34:43.417Z","updated":"2023-04-09T12:34:43.417Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":86921,"end":87183},{"type":"TextQuoteSelector","exact":"You can also use when conditional statements with your own defined variables.Keep in mind that conditionals require boolean inputs; that is, a test must eval-uate to true to trigger the condition and so, you need to use the bool filter withnon-boolean variables.","prefix":"ipped=0Using when with variables","suffix":"To demonstrate, take a look at t"}]}]}
>```
>%%
>*%%PREFIX%%ipped=0Using when with variables%%HIGHLIGHT%% ==You can also use when conditional statements with your own defined variables.Keep in mind that conditionals require boolean inputs; that is, a test must eval-uate to true to trigger the condition and so, you need to use the bool filter withnon-boolean variables.== %%POSTFIX%%To demonstrate, take a look at t*
>%%LINK%%[[#^lecaqs4nox|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^lecaqs4nox


>%%
>```annotation-json
>{"created":"2023-04-09T12:35:46.191Z","updated":"2023-04-09T12:35:46.191Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":88122,"end":88153},{"type":"TextQuoteSelector","exact":"Handling Exceptions with Blocks","prefix":"e keys\"when: keys is undefined69","suffix":"Now let’s talk about handling ex"}]}]}
>```
>%%
>*%%PREFIX%%e keys"when: keys is undefined69%%HIGHLIGHT%% ==Handling Exceptions with Blocks== %%POSTFIX%%Now let’s talk about handling ex*
>%%LINK%%[[#^gjjjalyig8i|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^gjjjalyig8i


>%%
>```annotation-json
>{"created":"2023-04-09T12:35:48.730Z","updated":"2023-04-09T12:35:48.730Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":88205,"end":88231},{"type":"TextQuoteSelector","exact":"Grouping tasks with blocks","prefix":" handling exceptions in Ansible.","suffix":"You can use blocks to group rela"}]}]}
>```
>%%
>*%%PREFIX%%handling exceptions in Ansible.%%HIGHLIGHT%% ==Grouping tasks with blocks== %%POSTFIX%%You can use blocks to group rela*
>%%LINK%%[[#^180xj6pr96w|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^180xj6pr96w


>%%
>```annotation-json
>{"created":"2023-04-09T12:35:55.152Z","updated":"2023-04-09T12:35:55.152Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":88231,"end":88354},{"type":"TextQuoteSelector","exact":"You can use blocks to group related tasks together. To demonstrate, take a lookat the following install-apache.yml playbook","prefix":"sible.Grouping tasks with blocks","suffix":":[elliot@control plays]$ cat ins"}]}]}
>```
>%%
>*%%PREFIX%%sible.Grouping tasks with blocks%%HIGHLIGHT%% ==You can use blocks to group related tasks together. To demonstrate, take a lookat the following install-apache.yml playbook== %%POSTFIX%%:[elliot@control plays]$ cat ins*
>%%LINK%%[[#^glpypq8lqc|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^glpypq8lqc


>%%
>```annotation-json
>{"created":"2023-04-09T13:02:27.678Z","updated":"2023-04-09T13:02:27.678Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":91588,"end":91616},{"type":"TextQuoteSelector","exact":"Handling failure with Blocks","prefix":"onfigured, listening on: port 80","suffix":"You can also use blocks to handl"}]}]}
>```
>%%
>*%%PREFIX%%onfigured, listening on: port 80%%HIGHLIGHT%% ==Handling failure with Blocks== %%POSTFIX%%You can also use blocks to handl*
>%%LINK%%[[#^ok51y6iulko|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^ok51y6iulko


>%%
>```annotation-json
>{"created":"2023-04-09T13:02:36.937Z","updated":"2023-04-09T13:02:36.937Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":91616,"end":91828},{"type":"TextQuoteSelector","exact":"You can also use blocks to handle task errors by using the rescue and always sec-tions. This is pretty much similar to exception handling in programming languageslike the try-catch in Java or try-except in Python","prefix":"t 80Handling failure with Blocks","suffix":".You can use the rescue section "}]}]}
>```
>%%
>*%%PREFIX%%t 80Handling failure with Blocks%%HIGHLIGHT%% ==You can also use blocks to handle task errors by using the rescue and always sec-tions. This is pretty much similar to exception handling in programming languageslike the try-catch in Java or try-except in Python== %%POSTFIX%%.You can use the rescue section*
>%%LINK%%[[#^3ab7rblu8o7|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^3ab7rblu8o7


>%%
>```annotation-json
>{"created":"2023-04-09T13:04:43.575Z","updated":"2023-04-09T13:04:43.575Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":95012,"end":95051},{"type":"TextQuoteSelector","exact":"Running Tasks upon Change with Handlers","prefix":"ection did (and will always)run.","suffix":"Now let’s demonstrate how you ca"}]}]}
>```
>%%
>*%%PREFIX%%ection did (and will always)run.%%HIGHLIGHT%% ==Running Tasks upon Change with Handlers== %%POSTFIX%%Now let’s demonstrate how you ca*
>%%LINK%%[[#^xwy3cleitu|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^xwy3cleitu


>%%
>```annotation-json
>{"created":"2023-04-09T13:04:45.007Z","updated":"2023-04-09T13:04:45.007Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":95135,"end":95161},{"type":"TextQuoteSelector","exact":"Running your first handler","prefix":"n tasks upon change in An-sible.","suffix":"You can use handlers to trigger "}]}]}
>```
>%%
>*%%PREFIX%%n tasks upon change in An-sible.%%HIGHLIGHT%% ==Running your first handler== %%POSTFIX%%You can use handlers to trigger*
>%%LINK%%[[#^ehjjgdqtb5|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^ehjjgdqtb5


>%%
>```annotation-json
>{"created":"2023-04-09T13:05:54.889Z","updated":"2023-04-09T13:05:54.889Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":96100,"end":96168},{"type":"TextQuoteSelector","exact":"RUNNING HANDLER [add elliot] ***********************changed: [node1]","prefix":"msg\": \"I am just another task.\"}","suffix":"PLAY RECAP *********************"}]}]}
>```
>%%
>*%%PREFIX%%msg": "I am just another task."}%%HIGHLIGHT%% ==RUNNING HANDLER [add elliot] ***********************changed: [node1]== %%POSTFIX%%PLAY RECAP **********************
>%%LINK%%[[#^qmg0mbopz9b|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^qmg0mbopz9b


>%%
>```annotation-json
>{"created":"2023-04-09T13:06:31.939Z","updated":"2023-04-09T13:06:31.939Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":96662,"end":96809},{"type":"TextQuoteSelector","exact":"Ansible playbooks and modules are idempotent which means that if a change inconfiguration occurred on the managed nodes; it will not redo it again!","prefix":"systemd-journal),1004(engineers)","suffix":"To fully understand the concept "}]}]}
>```
>%%
>*%%PREFIX%%systemd-journal),1004(engineers)%%HIGHLIGHT%% ==Ansible playbooks and modules are idempotent which means that if a change inconfiguration occurred on the managed nodes; it will not redo it again!== %%POSTFIX%%To fully understand the concept*
>%%LINK%%[[#^2r2crilk61|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^2r2crilk61


>%%
>```annotation-json
>{"created":"2023-04-09T13:22:43.902Z","updated":"2023-04-09T13:22:43.902Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":97527,"end":97562},{"type":"TextQuoteSelector","exact":"Controlling when to report a change","prefix":" add elliot handler did not run.","suffix":"You can use the changed_when key"}]}]}
>```
>%%
>*%%PREFIX%%add elliot handler did not run.%%HIGHLIGHT%% ==Controlling when to report a change== %%POSTFIX%%You can use the changed_when key*
>%%LINK%%[[#^gwppuxfijx6|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^gwppuxfijx6


>%%
>```annotation-json
>{"created":"2023-04-09T13:23:18.188Z","updated":"2023-04-09T13:23:18.188Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":99635,"end":99669},{"type":"TextQuoteSelector","exact":"Configuring services with handlers","prefix":"ult, handler1 was not triggered.","suffix":"Handlers are especially useful w"}]}]}
>```
>%%
>*%%PREFIX%%ult, handler1 was not triggered.%%HIGHLIGHT%% ==Configuring services with handlers== %%POSTFIX%%Handlers are especially useful w*
>%%LINK%%[[#^ityic5i5lt|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^ityic5i5lt


>%%
>```annotation-json
>{"created":"2023-04-09T13:23:28.259Z","updated":"2023-04-09T13:23:28.259Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":99669,"end":99861},{"type":"TextQuoteSelector","exact":"Handlers are especially useful when you are editing services configurations with An-sible. That’s because you only want to restart a service when there is a change inits service configuration.","prefix":"nfiguring services with handlers","suffix":"To demonstrate, take a look at t"}]}]}
>```
>%%
>*%%PREFIX%%nfiguring services with handlers%%HIGHLIGHT%% ==Handlers are especially useful when you are editing services configurations with An-sible. That’s because you only want to restart a service when there is a change inits service configuration.== %%POSTFIX%%To demonstrate, take a look at t*
>%%LINK%%[[#^5i72ohyce2|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^5i72ohyce2


>%%
>```annotation-json
>{"created":"2023-04-09T13:23:57.934Z","updated":"2023-04-09T13:23:57.934Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":102342,"end":102369},{"type":"TextQuoteSelector","exact":"Chapter 7: Jinja2 Templates","prefix":"ovided at the end of the book.82","suffix":"In the previous chapter, you lea"}]}]}
>```
>%%
>*%%PREFIX%%ovided at the end of the book.82%%HIGHLIGHT%% ==Chapter 7: Jinja2 Templates== %%POSTFIX%%In the previous chapter, you lea*
>%%LINK%%[[#^b4t69f8z76b|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^b4t69f8z76b


>%%
>```annotation-json
>{"created":"2023-04-09T13:24:07.790Z","updated":"2023-04-09T13:24:07.790Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":102782,"end":102811},{"type":"TextQuoteSelector","exact":"Accessing variables in Jinja2","prefix":"s and loop structures in Jinja2.","suffix":"Ansible will look for Jinja2 tem"}]}]}
>```
>%%
>*%%PREFIX%%s and loop structures in Jinja2.%%HIGHLIGHT%% ==Accessing variables in Jinja2== %%POSTFIX%%Ansible will look for Jinja2 tem*
>%%LINK%%[[#^5jt7by02fba|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^5jt7by02fba


>%%
>```annotation-json
>{"created":"2023-04-09T13:24:21.998Z","updated":"2023-04-09T13:24:21.998Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":102811,"end":102943},{"type":"TextQuoteSelector","exact":"Ansible will look for Jinja2 template files in your project directory or in a directorynamed templates under your project directory.","prefix":"a2.Accessing variables in Jinja2","suffix":"Let’s create a templates directo"}]}]}
>```
>%%
>*%%PREFIX%%a2.Accessing variables in Jinja2%%HIGHLIGHT%% ==Ansible will look for Jinja2 template files in your project directory or in a directorynamed templates under your project directory.== %%POSTFIX%%Let’s create a templates directo*
>%%LINK%%[[#^rnyk5ox2g|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^rnyk5ox2g


>%%
>```annotation-json
>{"created":"2023-04-09T13:26:48.386Z","updated":"2023-04-09T13:26:48.386Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":103333,"end":103560},{"type":"TextQuoteSelector","exact":"The inventory_hostname is another Ansible built-in (aka special or magic) vari-able that references the ‘current’ host being iterated over in the play. The web-server_message is a variable that you will define in your playbook.","prefix":"must end with the .j2 extension.","suffix":"Now go one step back to your pro"}]}]}
>```
>%%
>*%%PREFIX%%must end with the .j2 extension.%%HIGHLIGHT%% ==The inventory_hostname is another Ansible built-in (aka special or magic) vari-able that references the ‘current’ host being iterated over in the play. The web-server_message is a variable that you will define in your playbook.== %%POSTFIX%%Now go one step back to your pro*
>%%LINK%%[[#^sx0j47pfxco|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^sx0j47pfxco


>%%
>```annotation-json
>{"created":"2023-04-09T13:29:11.761Z","updated":"2023-04-09T13:29:11.761Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":105628,"end":105653},{"type":"TextQuoteSelector","exact":"Accessing facts in Jinja2","prefix":"am running to the finish line.85","suffix":"You can access facts in Jinja2 t"}]}]}
>```
>%%
>*%%PREFIX%%am running to the finish line.85%%HIGHLIGHT%% ==Accessing facts in Jinja2== %%POSTFIX%%You can access facts in Jinja2 t*
>%%LINK%%[[#^ds55id7hvzt|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^ds55id7hvzt


>%%
>```annotation-json
>{"created":"2023-04-09T13:29:54.222Z","updated":"2023-04-09T13:29:54.222Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":107832,"end":107864},{"type":"TextQuoteSelector","exact":"Conditional statements in Jinja2","prefix":"ess and process all the facts.87","suffix":"You can use the if conditional s"}]}]}
>```
>%%
>*%%PREFIX%%ess and process all the facts.87%%HIGHLIGHT%% ==Conditional statements in Jinja2== %%POSTFIX%%You can use the if conditional s*
>%%LINK%%[[#^f4omqetwmn5|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^f4omqetwmn5


>%%
>```annotation-json
>{"created":"2023-04-09T13:35:42.096Z","updated":"2023-04-09T13:35:42.096Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":110597,"end":110614},{"type":"TextQuoteSelector","exact":"Looping in Jinja2","prefix":" | rc=0 >>\"SELINUX IS ENABLED\"90","suffix":"You can use the for statement in"}]}]}
>```
>%%
>*%%PREFIX%%| rc=0 >>"SELINUX IS ENABLED"90%%HIGHLIGHT%% ==Looping in Jinja2== %%POSTFIX%%You can use the for statement in*
>%%LINK%%[[#^e5kkjg81iug|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^e5kkjg81iug


>%%
>```annotation-json
>{"created":"2023-04-09T13:36:10.777Z","updated":"2023-04-09T13:36:10.777Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":113828,"end":113852},{"type":"TextQuoteSelector","exact":"Chapter 8: Ansible Vault","prefix":"ovided at the end of the book.93","suffix":"There are many situations where "}]}]}
>```
>%%
>*%%PREFIX%%ovided at the end of the book.93%%HIGHLIGHT%% ==Chapter 8: Ansible Vault== %%POSTFIX%%There are many situations where*
>%%LINK%%[[#^j4ca9w6ahz|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^j4ca9w6ahz


>%%
>```annotation-json
>{"created":"2023-04-09T13:39:42.390Z","updated":"2023-04-09T13:39:42.390Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":114061,"end":114126},{"type":"TextQuoteSelector","exact":"Use Ansible Vault to protect and deal with sensitive information.","prefix":"is chapter, you will learn to:• ","suffix":"• Create, view, and edit vault e"}]}]}
>```
>%%
>*%%PREFIX%%is chapter, you will learn to:•%%HIGHLIGHT%% ==Use Ansible Vault to protect and deal with sensitive information.== %%POSTFIX%%• Create, view, and edit vault e*
>%%LINK%%[[#^d3eft4i2qm|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^d3eft4i2qm


>%%
>```annotation-json
>{"created":"2023-04-09T13:39:43.942Z","updated":"2023-04-09T13:39:43.942Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":114128,"end":114173},{"type":"TextQuoteSelector","exact":"Create, view, and edit vault encrypted files.","prefix":"al with sensitive information.• ","suffix":"• Decrypt vault encrypted files "}]}]}
>```
>%%
>*%%PREFIX%%al with sensitive information.•%%HIGHLIGHT%% ==Create, view, and edit vault encrypted files.== %%POSTFIX%%• Decrypt vault encrypted files*
>%%LINK%%[[#^zdtmt59dbb8|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^zdtmt59dbb8


>%%
>```annotation-json
>{"created":"2023-04-09T13:39:47.891Z","updated":"2023-04-09T13:39:47.891Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":114175,"end":114256},{"type":"TextQuoteSelector","exact":"Decrypt vault encrypted files and to change the password of a vault encryptedfile","prefix":"nd edit vault encrypted files.• ","suffix":".Furthermore, you will learn how"}]}]}
>```
>%%
>*%%PREFIX%%nd edit vault encrypted files.•%%HIGHLIGHT%% ==Decrypt vault encrypted files and to change the password of a vault encryptedfile== %%POSTFIX%%.Furthermore, you will learn how*
>%%LINK%%[[#^lj33m558i2f|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^lj33m558i2f


>%%
>```annotation-json
>{"created":"2023-04-09T13:39:52.853Z","updated":"2023-04-09T13:39:52.853Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":114345,"end":114369},{"type":"TextQuoteSelector","exact":"Creating encrypted files","prefix":"es and files in your play-books.","suffix":"To create a new encrypted file; "}]}]}
>```
>%%
>*%%PREFIX%%es and files in your play-books.%%HIGHLIGHT%% ==Creating encrypted files== %%POSTFIX%%To create a new encrypted file;*
>%%LINK%%[[#^xiq8mbdy8i|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^xiq8mbdy8i


>%%
>```annotation-json
>{"created":"2023-04-09T13:40:11.680Z","updated":"2023-04-09T13:40:11.680Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":116651,"end":116677},{"type":"TextQuoteSelector","exact":"Decrypting encrypted files","prefix":"password-file secret-vault.txt95","suffix":"Let’s create another encrypted f"}]}]}
>```
>%%
>*%%PREFIX%%password-file secret-vault.txt95%%HIGHLIGHT%% ==Decrypting encrypted files== %%POSTFIX%%Let’s create another encrypted f*
>%%LINK%%[[#^3vulb2f0e0c|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^3vulb2f0e0c


>%%
>```annotation-json
>{"created":"2023-04-09T13:40:25.149Z","updated":"2023-04-09T13:40:25.149Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":117597,"end":117634},{"type":"TextQuoteSelector","exact":"Changing an encrypted file's password","prefix":"t2.txt is no longer encrypted.96","suffix":"You can also encrypt existing fi"}]}]}
>```
>%%
>*%%PREFIX%%t2.txt is no longer encrypted.96%%HIGHLIGHT%% ==Changing an encrypted file's password== %%POSTFIX%%You can also encrypt existing fi*
>%%LINK%%[[#^5e7489lmexo|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^5e7489lmexo


>%%
>```annotation-json
>{"created":"2023-04-09T13:42:19.567Z","updated":"2023-04-09T13:42:19.567Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":118555,"end":118598},{"type":"TextQuoteSelector","exact":"Decrypting content at run time in playbooks","prefix":"d before entering the new one.97","suffix":"You can use vault encrypted file"}]}]}
>```
>%%
>*%%PREFIX%%d before entering the new one.97%%HIGHLIGHT%% ==Decrypting content at run time in playbooks== %%POSTFIX%%You can use vault encrypted file*
>%%LINK%%[[#^r8sxgrlbcl|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^r8sxgrlbcl


>%%
>```annotation-json
>{"created":"2023-04-09T13:43:13.804Z","updated":"2023-04-09T13:43:13.804Z","document":{"title":"learn_ansible_quickly.pdf","link":[{"href":"urn:x-pdf:f7e0c3b640379c0f263e43eee1b1f3b9"},{"href":"vault:/Books/learn_ansible_quickly.pdf"}],"documentFingerprint":"f7e0c3b640379c0f263e43eee1b1f3b9"},"uri":"vault:/Books/learn_ansible_quickly.pdf","target":[{"source":"vault:/Books/learn_ansible_quickly.pdf","selector":[{"type":"TextPositionSelector","start":119611,"end":119691},{"type":"TextQuoteSelector","exact":"Now run the playbook again but pass the --ask-vault-pass option this time around","prefix":"decryptthe web-secrets.yml file.","suffix":":98[elliot@control plays]$ ansib"}]}]}
>```
>%%
>*%%PREFIX%%decryptthe web-secrets.yml file.%%HIGHLIGHT%% ==Now run the playbook again but pass the --ask-vault-pass option this time around== %%POSTFIX%%:98[elliot@control plays]$ ansib*
>%%LINK%%[[#^dsbssu4wvug|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^dsbssu4wvug
