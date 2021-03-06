aws
===

The Amazon Web Services (AWS) provider manages multiple types of resources.

aws_ec2
-------

AWS Instances can be provisioned using this resource.

* :docs1.5:`Topology Example <workspace/topologies/aws-ec2-new.yml>`
* :docs1.5:`Topology Example w/ VPC <workspace/topologies/aws-ec2-vpc.yml>`
* `aws_ec2 module <http://docs.ansible.com/ansible/latest/ec2_module.html>`_

EC2 Inventory Generation
~~~~~~~~~~~~~~~~~~~~~~~~

If an instance has a public IP attached, its hostname in public DNS, if
available, will be provided in the generated Ansible inventory file, and if not
the public IP address will be provided.

For instances which have a private IP address for VPC usage, the private IP
address will be provided since private EC2 DNS hostnames (e.g.
**ip-10-0-0-1.ec2.internal**) will not typically be resolvable outside of AWS.

For instances with both a public and private IP address, the public address is
always provided instead of the private address, so as to avoid duplicate runs
of Ansible on the same host via the generated inventory file.

aws_ec2_key
-----------

AWS SSH keys can be added using this resource.

* :docs1.5:`Topology Example <workspace/topologies/aws-ec2-key-new.yml>`
* `ec2_key module <http://docs.ansible.com/ansible/latest/ec2_key_module.html>`_

.. note:: This resource will not be torn down during a :term:`destroy`
   action. This is because other resources may depend on the now existing
   resource.

aws_s3
------

AWS Simple Storage Service buckets can be provisioned using this resource.

* :docs1.5:`Topology Example <workspace/topologies/aws-s3-new.yml>`
* `aws_s3 module <http://docs.ansible.com/ansible/latest/aws_s3_module.html>`_

.. note:: This resource will not be torn down during a :term:`destroy`
   action. This is because other resources may depend on the now existing
   resource.

aws_sg
------

AWS Security Groups can be provisioned using this resource.

* :docs1.5:`Topology Example <workspace/topologies/aws-sg-new.yml>`
* `ec2_group module <http://docs.ansible.com/ansible/latest/ec2_group_module.html>`_

.. note:: This resource will not be torn down during a :term:`destroy`
   action. This is because other resources may depend on the now existing
   resource.

Additional Dependencies
-----------------------

No additional dependencies are required for the AWS Provider.

Credentials Management
----------------------

AWS provides several ways to provide credentials. LinchPin supports
some of these methods for passing credentials for use with AWS resources.

One method to provide AWS credentials that can be loaded by LinchPin is to use
the INI format that the `AWS CLI tool
<https://docs.aws.amazon.com/cli/latest/userguide/cli-config-files.html>`_
uses.

Environment Variables
~~~~~~~~~~~~~~~~~~~~~

LinchPin honors the AWS environment variables

Provisioning
~~~~~~~~~~~~

Provisioning with credentials uses the ``--creds-path`` option.

.. code-block:: bash

   $ linchpin -v --creds-path ~/.config/aws up

Alternatively, the credentials path can be set as an environment variable,

.. code-block:: bash

   $ export CREDS_PATH="~/.config/aws"
   $ linchpin -v up

