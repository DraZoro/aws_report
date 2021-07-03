README: ebs-report - Creates a report about EBS volumes in account, with tracking of snapshots per volume

License: You can use/modify/circulate or do whatever you want.
         Just note that this script is given "As Is" without any warranty


Requirements:

    Needs python 2.7.3 or newer (not python 3)
    boto library (at least 2.31.1). Can be dowmloaded here:
        https://pypi.python.org/pypi/boto/#downloads

USAGE: ebs-report.py [-h] [--regions REGIONS] [--access_key ACCESS_KEY]
                     [--secret_key SECRET_KEY] --file FILE

Creates a CSV report about EBS volumes and tracks snapshots on them.

optional arguments:
  -h, --help            show this help message and exit
  --regions REGIONS     AWS regions to create the report on, can add multiple
                        with | as separator. Default will assume all regions
  --access_key ACCESS_KEY
                        AWS API access key. If missing default is used
  --secret_key SECRET_KEY
                        AWS API secret key. If missing default is used
  --file FILE           Path for output CSV file
        
           
Defaults:

    At the top of the script there are 3 default definitions:
    AWS_ACCESS_KEY - default access key. If the scripts runs on an instance with a sufficient
                 IAM role, it can be left as None and will work. If not can be switched to
                 AWS_ACCESS_KEY = 'AKIAIVXXXXXXN3G3N32Q'
    AWS_SECRET_KEY - default secret key. If the scripts runs on an instance with a sufficient
                 IAM role, it can be left as None and will work. If not can be switched to
                 AWS_ACCESS_KEY = 'UGSYQL6PXXXXXXXXXX0Bf0bS/S+OwnA2GrJ0MOY4Y'
                 
    AWS_REGIONS - defualt regions in case --region is dropped. example:
                 AWS_REGIONS = u'us-east-1|us-west-1'   
    
           
Example:

    python ebs-report.py --regions us-east-1 --access_key AKIAIXXXXXXXXXX3N32Q 
                         --secret_key UGSYXXXXXXXXXXXXXXBf0bS/S+OwnA2GrJ0MOY4Y --file d:\my-ebs-report-July-2014.csv
    
