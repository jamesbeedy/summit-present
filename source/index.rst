.. revealjs:: Putting LXD to Work

    James Beedy
    9/13/2016

    Juju Charmer Summit

    `https://github.com/jamesbeedy/summit-present <https://github.com/jamesbeedy/summit-present>`_

    Associated Materials

    `https://jujucharms.com <https://jujucharms.com>`_

.. revealjs:: About Me

    Cloud Engineer/DevOps Engineer

    Sys admin, net admin, storage admin, hacker, stacker

     
.. revealjs:: The beginning

  .. rst-class:: fragment

      2009 VMWare - ESXi

      OFA,OVF

      Machine spec templates

      2012 Openstack Essex Release

      Handroll

      Devstack/vagrant

      Templates

      Chef, Ansible, Puppet

      ...

      -> Juju

.. revealjs:: Juju - Big Software - Modeling
 :title-heading: h3

  .. rst-class:: fragment

      Openstacks, Big Data stacks, Web Applications!

      Abstract from cfgmgmt --> save cycles!

      Model complex environments!

      Replicable environments across heterogeneous providers!

.. revealjs:: Why Juju? 
 :subtitle: We must have service resiliency, why not stand on the shoulders of giants too?

  .. rst-class:: fragment

  .. list-table::

   * - Environment Lifecycle
   * - Built-ins - service discovery, leader election, 
   * - Community Driven


.. revealjs:: Essentials
 :subtitle: Let us deploy, but first ...


 .. rst-class:: fragment

       - zfs
       - local apt cache
       - reverse proxy


.. revealjs:: apt-cacher-ng
 :subtitle: pass-through https

 .. rv_code::

     # acng.conf

     PassThroughPattern: .*:443$


.. revealjs:: Reverse Proxy
 :subtitle: Give us access to our damn containers!

    Port based, or domain based routing is a great way to access your containers!
    This can be accomplished by a means of your choosing, generally I find NGINX, and/or HAProxy to be sufficient.

 .. rst-class:: fragment

    - NGINX
    - HAPROXY
    

.. revealjs:: Application Environments = Juju models
 :title-heading: h2
 :subtitle: Juju models are a great way to separate app environments 
 :subtitle-heading: h4

  .. rst-class:: fragment

      * - Test Environment
        - cache - LXD
        - database - LXD
        - 1/per dev - webapp - LXD


      * - Development Environment
        - cache - LXD
        - database - LXD
        - webapp - LXD


      * - Staging Environment
        - 3x cache - LXD
        - database - LXD
        - 3x webapp - LXD


      * - Production Environment
        - 3x cache - AWS
        - 3x database - AWS
        - 3x webapp - AWS

.. revealjs:: Test Env
 :title-heading: h2
 :subtitle: 
 :subtitle-heading: h4

 .. image:: _images/webapp-MIN.png
    :width: 800
    :height: 550
    :alt: PRMMIN


.. revealjs:: Staging Env
 :title-heading: h2
 :subtitle: 
 :subtitle-heading: h4

 .. image:: _images/webapp-MED.png
    :width: 800
    :height: 550
    :alt: PRMMED


.. revealjs:: Production Env
 :title-heading: h2
 :subtitle: 
 :subtitle-heading: h4

 .. image:: _images/webapp-MAX.png
    :width: 600
    :height: 550
    :alt: PRMMAX

.. revealjs:: Questions?


  `@jamesbeedy <http://twitter.com/jamesbeedy>`_

  `github <http://github.com/jamesbeedy>`_

  `bdx on irc`

 .. image:: _images/system76_logo_primary.png
    :width: 600
    :height: 550
    :alt: system76



