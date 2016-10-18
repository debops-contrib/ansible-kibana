Default variable details
========================

.. include:: includes/all.rst

Some of ``debops-contrib.kibana`` default variables have more extensive
configuration than simple strings or lists, here you can find documentation and
examples for them.

.. contents::
   :local:
   :depth: 1


.. _kibana__ref_service_configuration:

kibana__service_configuration
-----------------------------

This is a YAML configuration dictionary which is used to set any custom options
into :file:`kibana.yml`. Simply add the upstream configuration key and value
to this dictionary. An overview of the supported properties can be found in
the `Kibana Server Properties <https://www.elastic.co/guide/en/kibana/4.6/kibana-server-properties.html>`_
documentation.

Example
~~~~~~~

Customize the Elasticsearch HTTP URL to which Kibana should connect:

.. code-block:: yaml

   kibana__service_configuration:
     elasticsearch.url: 'http://elastic01.example.com:9200'

.. note::

    Some server properties will be set implicitly according to the Ansible role
    configuration. The following variables should be used instead:

    - :envvar:`kibana__bind` for ``server.host``
    - :envvar:`kibana__port` for ``server.port``
