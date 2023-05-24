## 1.How to optimize PySpark jobs
- USing RDD Data set
- Persistent cache: we can cache repitative task. PErsist within the disk. If you go and save in hDD/ROM is disk if you in RAM its catche
- Serialization: decide in configuration
- broadcaset variable and join: storing data in node itself no need to visit  worker node
- Lazy evaluation: Excution will not start until an action is triggered. EX. Df have filter again select column and so on 
when you want to display it will compute

- Why do want to persistsL
First we don't persist, we first store data in temp rdds for heavy lifting . FInally when I use zto show result I will use these rdds
- For scheduler we have use Azur logic apps but now we use Azure scheduler
I have also worked on airflow
- Diff between group by key and reduce by key 
  - helps optimization and deshufflinf
  - wide Reduceby key key differnce  
  - group by doesnot mapside combine and reduceby does mapside comnbine. preffered one is reduceby for optimization
-  Usecase for Azure functions: its a trigger. we run pipeline if the files is changing for cost optimization 
-  Data validation and data checking process: we have error log table 
-   what is brodcasting in python: its variable or join when we 
 -    
