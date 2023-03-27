# mstical_queries
My queries to use with Msticpy it is broken down into the following basic design

Top Level Folder = Vendor

Within that subfolder are multiple yaml files which contain custom queries.

As you can see, specific queries are grouped into mitre, for example there is a query looking for suspicious child processes from office applications called office_applications_suspicious_child stored within the mstical_execution.yaml file. These queries are more basic and designed to provide a small subset of data which you may find worth investigating as you would consider it suspicious. These queries can ideally be ran in an automated way with the data collected daily and turned into automated “hunting leads” for an analyst to investigate as lower fidelity than a traditional SOC alert, with the whitelisting done directly within a notebook or function.

There is also a file called mstical_host_triage. Which has various single endpoint specific queries desgined to be executed to contextualise what activity has occured on a host, in combination with the triage Jupyter notebook.

Alternatively an analyst can pick a query for each mitre category when performing ad-hoc hunting, or whatever else they want to do with them.

More “generic” queries are grouped based on the data type requested. For example if you want to request anything to do with processes such as parent process = rundll32.exe you would use the parent_processes_query in process.yaml. These queries are designed to gather a larger dataset to perform more complex investigations, involving machine learning and data science techniques, or build baselines, such as all rundll32 activity or net.exe, psexec etc. These queries should be utilised for the detection of anomalies within a specific environment in mind.


PRs welcome
