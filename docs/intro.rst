Introduction
============

Installation
------------

This package is available on  ``pip``::

    pip install pydeohub

Requirements
------------
Pydeohub was developed with Python 3.9 but contains no external dependencies so should be compatiable with all current versions of Python 3.7+.

The Smart Videohub you're using should be fully updated, this library was developed on a `Smart Videohub 20x20 <https://www.blackmagicdesign.com/products/smartvideohub/techspecs/W-VHS-02>`_ but should be compatiable with all recent Smart Videohub models with an ethernet connection.

Getting Started
----------------
The following code example shows how to initiate a connection with a Videohub::
    
    from pydeohub import Videohub

    hub = Videohub('192.168.0.150')

=================
Routing
=================
There are two way to re-route inputs and outputs on the Smart Videohub, individual changes or bulk changes::

    hub.route(0, 0) # Routes Input 1 to Output 1

    bulk_routes = [
        (0, 0),
        (1, 1),
        (2, 2),
        (3, 3),
        (4, 4),
        (5, 5)
    ]
    hub.bulk_route(bulk_routes) # Routes Inputs 1-6 to Outputs 1-6

.. note:: All input and output identifiers are 0-indexed so 'Input 1' is actually identifier `0`.

=================
Labels
=================
Each input and output has an associated label that is displayed on the Videohub's built-in display and most accompying Blackmagic software integrations.  Pydeohub can modify these labels programatically::

    hub.input_label(0, 'Camera 1') # Label Input 1 as Camera 1

    hub.output_label(19, 'Main TV') # Label Output 20 as Main TV

