.. IntStream documentation master file, created by
   sphinx-quickstart on Fri Feb 26 02:53:58 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

.. role:: python(code)
   :language: python

.. role:: bash(code)
   :language: bash


Hunting Job
#############

.. contents:: Contents
   :depth: 3
   :backlinks: top


Collects information on indicator

Develop Hunting Job
=====================

:bash:`intstreamsdk` is a python library that makes interacting with the IntStream api much easier.

1. create a virtual environment and install :bash:`instreamsdk`
2. create a :bash:`indicatorjob.py` script

.. code:: python 

  from intstreamsdk.job import IndicatorJob
  from intstreamsdk.client import SyncClient
  from intstreamsdk import resource
  class IPv4Job(IndicatorJob):
      def __init__(self, client_class):
          super(IPv4Job, self).__init__(client_class)

      def custom(self, parsed_args):
          # retrieve id
          ipv4 = parsed_args.indicator
          data = self.check_upload([ipv4], resource.IPV4)
          indicator_id = data[0]["id"]

          COL = "category"
          upsert = resource.ColumnGetPerform(self.client)
          # here query some system to get the category
          category = "Business; Technology"
          # save to databasennn
          upsert.upsert(resource.IndicatorTextField, COL, category, indicator_id)


  if __name__ == "__main__":
      # set env variables:
      # JOB_USERNAME
      # JOB_PASSWORD
      # JOB_SERVER_URL - base server url

      # initialize job object     with SyncClient or AsyncClient
      demo = IPv4Job(SyncClient)
      # add any
      demo.run()

3. set JOB_USERNAME, JOB_PASSWORD, and JOB_SERVER_URL environment variables
4. run :bash:`python indicatorjob.py` to test your job
5. create a :bash:`requirements.txt` file in the same directory as :bash:`indicatorjob.py`
6. :bash:`tar -czf job.tar.gz requirments.txt indicatorjob.py`
   
Install / Cron Schedule
=======================

1. Go to Sources | Hunting jobs. 
2. Fill in name.
3. Add version. 
4. upload :bash:`job.tar.gz`
