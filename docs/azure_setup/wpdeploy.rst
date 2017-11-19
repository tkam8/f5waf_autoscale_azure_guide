.. _module1:

WORDPRESS インスタンスのデプロイ
====================================================

.. graphviz::

   digraph breadcrumb {
      rankdir="LR"
      ranksep=.4
      node [fontsize=10,style="rounded,filled",shape=box,color=gray72,margin="0.05,0.05",height=0.1] 
      fontname = "arial-bold" 
      fontsize = 10
      labeljust="l"
      subgraph cluster_provider {
         style = "rounded,filled"
         color = lightgrey
         height = .75
         label = "Provider"
         bigip [label="BIG-IP",color="steelblue1"]
         iapps [label="iApp Templates&#92;n& Deployments"]
         iwf_templates [label="Service&#92;nTemplates"]
      }
      subgraph cluster_tenant {
         style = "rounded,filled"
         color = lightgrey
         height = .75
         label = "Tenant"
         iwf_catalog [label="Service&#92;nCatalog"]
         iwf_deploy [label="Service&#92;nDeployment"]
      }
      iwf_deploy -> iwf_catalog -> iwf_templates -> iapps -> bigip
   }


.. NOTE:: In order to confirm the results of REST API calls made in this lab, it's 
   recommended to keep GUI/SSH sessions to BIG-IP and iWorkflow devices open. 
   By default, BIG-IP and iWorkflow will log all the REST API related events locally 
   to **restjavad.0.log** . These logs can also be directed to a remote syslog server 
   (see https://support.f5.com/csp/article/K13080). On a side note, the **ltm** 
   log files listed below contains log messages specific to  BIG-IP local 
   traffic management events. 


