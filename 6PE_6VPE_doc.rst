6PE/6VPE Functions
===================

.. role:: orange

sth::emulation_6pe_6vpe_provider_port_config
---------------------------------------------------
 
Purpose
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

:orange:`Spirent Extension (for Spirent HLTAPI only).`

   
Configures or deletes an emulated provider-side test port

Synopsis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. parsed-literal::


 sth::emulation_6pe_6vpe_provider_port_config
   -mode create -port_handle <port_handle> | -mode delete -handle <handle>
   [:ref:`-dut_interface_ipv4_addr <dut_interface_ipv4_addr_emulation_6pe_6vpe_provider_port_config>` <a.b.c.d>]
   [:ref:`-dut_interface_ipv4_addr_step <dut_interface_ipv4_addr_step_emulation_6pe_6vpe_provider_port_config>` <a.b.c.d>]
   [:ref:`-dut_interface_ipv4_prefix_len <dut_interface_ipv4_prefix_len_emulation_6pe_6vpe_provider_port_config>` <0-32>]
   [:ref:`-sub_interface_enable <sub_interface_enable_emulation_6pe_6vpe_provider_port_config>` {true|false}]
   [:ref:`-sub_interface_count <sub_interface_count_emulation_6pe_6vpe_provider_port_config>` <0-255>]
   [:ref:`-vlan_id <vlan_id_emulation_6pe_6vpe_provider_port_config>` <0-4095>]

Arguments
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. _port_handle_emulation_6pe_6vpe_provider_port_config:

.. option:: -port_handle

                 Specifies the test port to be added to the provider side of the
                 6PE/6VPE network. This argument is mandatory for -mode create.
 
.. _mode_emulation_6pe_6vpe_provider_port_config:

.. option:: -mode

                 Specifies the action to be performed. This argument is mandatory.
                 Possible values are described below::
                 
                  create     Adds a provider-side test port. You must specify
                             -port_handle.
                  
                  delete     Deletes specified routers under the provide-side port.
                             You must specify -handle. 
 
.. _handle_emulation_6pe_6vpe_provider_port_config:

.. option:: -handle

                 Specifies the handle of routers created under the emulated test
                 port. This argument is mandatory for -mode delete.
  
.. _dut_interface_ipv4_addr_emulation_6pe_6vpe_provider_port_config:

.. option:: -dut_interface_ipv4_addr

                 Defines the first IPv4 address of the DUT interfaces connected to
                 the port. The default value is 192.85.1.1. 
  
.. _dut_interface_ipv4_addr_step_emulation_6pe_6vpe_provider_port_config:

.. option:: -dut_interface_ipv4_addr_step

                 Specifies the step size by which the DUT IPv4 address is
                 incremented. The default value is 0.0.1.0. The number of times
                 that the step repeats is the same as the number of
                 sub-interfaces. This argument is available when
                 -sub_interface_enable is set to true.
 
.. _dut_interface_ipv4_prefix_len_emulation_6pe_6vpe_provider_port_config:

.. option:: -dut_interface_ipv4_prefix_len

                 Specifies the IPv4 address prefix length of DUT interface
                 connected to the port. Possible values range from 0 to 32. The
                 default value is 24.
  
.. _sub_interface_enable_emulation_6pe_6vpe_provider_port_config:

.. option:: -sub_interface_enable

                 Enables or disables sub-interface on the DUT. Possible values are
                 true and false. The default value is false. When this argument is
                 enabled, you can specify the following arguments::
                  
                  -sub_interface_count
                  -dut_interface_ipv4_addr_step
                  -vlan_id
                  -vlan_id_step
  
.. _sub_interface_count_emulation_6pe_6vpe_provider_port_config:

.. option:: -sub_interface_count

                 Defines the number of sub-interfaces on the DUT interface.
                 Possible values range from 1 to 255. The default value is 1. This
                 argument is available when -sub_interface_enable is set to true.
  
.. _vlan_id_emulation_6pe_6vpe_provider_port_config:

.. option:: -vlan_id

                 Specifies the starting VLAN ID of DUT interfaces. Possible values
                 range from 0 to 4095. The default value is 1. This argument is
                 available when -sub_interface_enable is set to true.
  
.. _vlan_id_step_emulation_6pe_6vpe_provider_port_config:

.. option:: -vlan_id_step

                 Specifies the step size by which the VLAN ID is incremented.
                 Possible values range from 0 to 4095. The default value is 1.
                 This argument is available when -sub_interface_enable is set to
                 true.

Return Values
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Depending on the specific language that HLTAPI uses, the function returns a keyed
list/dictionary/hash (See Introduction for more information on return value formats)
using the following keys (with corresponding data)::

  status          Success (1) or failure (0) of the operation

  log             An error message (if the operation failed)


Description
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The ``sth::emulation_6pe_6vpe_provider_port_config`` function configures an emulated
provider-side port, or deletes the routers under the port (specified by -handle).
Use the -port_handle argument to specify the port to be added. Use the -action
argument to specify the action to perform.   

Examples
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 
The following example configures a provider-side port::
   
 sth::emulation_6pe_6vpe_provider_port_config 
     -port_handle                        $port1
     -mode                               create 
     -dut_interface_ipv4_addr            192.86.1.1 
     -dut_interface_ipv4_addr_step        0.0.2.0 
     -dut_interface_ipv4_prefix_len      24 
     -sub_interface_enable               true 
     -sub_interface_count                 10 
     -vlan_id                            102 
     -vlan_id_step                       2   

Sample output::
 
         {status 1}


sth::emulation_6pe_6vpe_cust_port_config
---------------------------------------------------

Purpose
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

:orange:`Spirent Extension (for Spirent HLTAPI only).`

 
Configures or deletes an emulated customer-side test port
 
Synopsis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. parsed-literal::


 sth::emulation_6pe_6vpe_cust_port_config
     -mode create -port_handle <port_handle> |-mode delete -handle <handle>
     [:ref:`-dut_interface_ipv6_addr <dut_interface_ipv6_addr_emulation_6pe_6vpe_cust_port_config>` <aaaa.bbbb.cccc.dddd.eeee.ffff.gggg.hhhh>]
     [:ref:`-dut_interface_ipv6_addr_step <dut_interface_ipv6_addr_step_emulation_6pe_6vpe_cust_port_config>` <aaaa.bbbb.cccc.dddd.eeee.ffff.gggg.hhhh>]
     [:ref:`-dut_interface_ipv6_prefix_len <dut_interface_ipv6_prefix_len_emulation_6pe_6vpe_cust_port_config>` <1-128>]
     [:ref:`-sub_interface_enable <sub_interface_enable_emulation_6pe_6vpe_cust_port_config>` {true|false}]
     [:ref:`-sub_interface_count <sub_interface_count_emulation_6pe_6vpe_cust_port_config>` <0-255>]
     [:ref:`-vlan_id <vlan_id_emulation_6pe_6vpe_cust_port_config>` <0-4095>]
     [:ref:`-vlan_id_step <vlan_id_step_emulation_6pe_6vpe_cust_port_config>` <0-4095>]

Arguments
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. _port_handle_emulation_6pe_6vpe_cust_port_config:

.. option:: -port_handle

                 Specifies the test port to be added to the customer side of the
                 6PE/6VPE network. This argument is mandatory for -mode create.

.. _mode_emulation_6pe_6vpe_cust_port_config:

.. option:: -mode

                 Specifies the action to be performed. This argument is mandatory.
                 Possible values are described below::
                 
                  create Adds a customer-side test port. You must specify
                  -port_handle.
                  
                  delete   Deletes specified routers under the customer-side port.
                                 You must specify -handle.
                           

.. _handle_emulation_6pe_6vpe_cust_port_config:

.. option:: -handle

                 Specifies the handle of the CE routers. This argument is
                 mandatory for -mode delete.

.. _dut_interface_ipv6_addr_emulation_6pe_6vpe_cust_port_config:

.. option:: -dut_interface_ipv6_addr

                 Specifies the first IPv6 address of the DUT interfaces connected
                 to the port. The default value is ::.

.. _dut_interface_ipv6_addr_step_emulation_6pe_6vpe_cust_port_config:

.. option:: -dut_interface_ipv6_addr_step

                 Specifies the step value by which to increment subsequent DUT
                 IPv6 addresses. This argument is only available when
                 -sub_interface_enable is set to true. The default value is
                 0:0:0:1::.

.. _dut_interface_ipv6_prefix_len_emulation_6pe_6vpe_cust_port_config:

.. option:: -dut_interface_ipv6_prefix_len

                 Specifies the IPv6 address's prefix length of the DUT connected
                 to the port. Possible values range from 1 to 128. The default
                 value is 64.

.. _sub_interface_enable_emulation_6pe_6vpe_cust_port_config:

.. option:: -sub_interface_enable

                 Enables or disables sub-interfaces on the DUT interface.
                 Possible values are true and false. The default value is false.
                   
.. _sub_interface_count_emulation_6pe_6vpe_cust_port_config:

.. option:: -sub_interface_count

                 Defines the number of sub-interfaces to be created for the DUT.
                 Possible values range from 1 to 255. The default value
                 is 1. This argument is available when -sub_interface_enable is
                 set to true.

.. _vlan_id_emulation_6pe_6vpe_cust_port_config:

.. option:: -vlan_id

                 Specifies the starting VLAN ID. Possible values
                 range from 0 to 4095. The default value is 1. This argument is
                 available when -sub_interface_enable is set to true.
 
.. _vlan_id_step_emulation_6pe_6vpe_cust_port_config:

.. option:: -vlan_id_step

                 Defines the step size by which to increment the VLAN ID. Possible
                 values range from 0 to 4095. The default value is 1. This
                 argument is available when -sub_interface_enable is set to true.

Return Values
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Depending on the specific language that HLTAPI uses, the function returns a keyed
list/dictionary/hash (See Introduction for more information on return value
formats) using the following keys (with corresponding data)::

  status          Success (1) or failure (0) of the operation

  log             An error message (if the operation failed)


Description
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The ``sth::emulation_6pe_6vpe_cust_port_config`` function configures an emulated
customer-side port, or deletes the routers under the port (specified by -handle).
Use the -port_handle argument to specify the port to be added. Use the -action
argument to specify the action to perform. 

Examples
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

   
The following example configures a customer-side port::
     
     sth::emulation_6pe_6vpe_cust_port_config 
         -port_handle                     $port2
         -mode                            create 
         -dut_interface_ipv6_addr          2000::10 
         -dut_interface_ipv6_addr_step     ::1 
         -dut_interface_ipv6_prefix_len    96 
         -sub_interface_enable             true 
         -sub_interface_count              10 
         -vlan_id                          102 
         -vlan_id_step                     2 

Sample output::

     {status 1}



sth::emulation_6pe_6vpe_config
---------------------------------------------------

Purpose
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


:orange:`Spirent Extension (for Spirent HLTAPI only).`

  
Creates or deletes IPv6 Provider Edge Router (6PE) or IPv6 VPN Provider Edge
Router (6VPE) network topologies, mapping the operations of the 6PE or 6VPE Wizard in
the Spirent TestCenter GUI.
   
The function creates emulated and simulated Customer Edge (CE), Provider (P), and
Provider Edge (PE) routers, specifies and enables routing and labeling protocols,
configures customer and provider side VPNs, and creates the traffic that is sent
between VPNs. 

Synopsis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. parsed-literal::


 sth::emulation_6pe_6vpe_config
     -handle  <handle>
     -mode  <create|delete>
     [:ref:`-dut_router_id <dut_router_id_emulation_6pe_6vpe_config>`  <a.b.c.d>]
     [:ref:`-dut_as <dut_as_emulation_6pe_6vpe_config>`  <1-65535>]
     [:ref:`-dut_4byte_as_enable <dut_4byte_as_enable_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-dut_4byte_as <dut_4byte_as_emulation_6pe_6vpe_config>`  <65535:65535>]
     [:ref:`-use_cust_ports <use_cust_ports_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-use_provider_ports <use_provider_ports_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-igp_protocol <igp_protocol_emulation_6pe_6vpe_config>`  {ospf|isis|rip|none}]
     [:ref:`-mpls_protocol <mpls_protocol_emulation_6pe_6vpe_config>`  {none|ldp|rsvp|ospf|isis}]
     
     IGP OSPF Router Generation Parameters
 
     [:ref:`-igp_ospf_area_id <igp_ospf_area_id_emulation_6pe_6vpe_config>`  <a.b.c.d>]
     [:ref:`-igp_ospf_network_type <igp_ospf_network_type_emulation_6pe_6vpe_config>`  {native|broadcast|p2p}]
     [:ref:`-igp_ospf_router_priority <igp_ospf_router_priority_emulation_6pe_6vpe_config>`  <0-255>] 
     [:ref:`-igp_ospf_interface_cost <igp_ospf_interface_cost_emulation_6pe_6vpe_config>`  <1-65535>]
     [:ref:`-igp_ospf_options <igp_ospf_options_emulation_6pe_6vpe_config>`  <0 -  0x7f >]
     [:ref:`-igp_ospf_auth_mode <igp_ospf_auth_mode_emulation_6pe_6vpe_config>`  {none|simple|md5}]
     [:ref:`-igp_ospf_auth_password <igp_ospf_auth_password_emulation_6pe_6vpe_config>`  <password>]
     [:ref:`-igp_ospf_auth_md5_key <igp_ospf_auth_md5_key_emulation_6pe_6vpe_config>`  <0-255>]
     [:ref:`-igp_ospf_graceful_restart_enable <igp_ospf_graceful_restart_enable_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-igp_ospf_graceful_restart_type <igp_ospf_graceful_restart_type_emulation_6pe_6vpe_config>`  {none|rfc_standard|ll_signalling}]
     [:ref:`-igp_ospf_bfd_enable <igp_ospf_bfd_enable_emulation_6pe_6vpe_config>`  {true|false}]
 
     IGP ISIS Router Generation Parameters
 
     [:ref:`-igp_isis_level <igp_isis_level_emulation_6pe_6vpe_config>`  {level1|level2|level1_and_2}]
     [:ref:`-igp_isis_network_type <igp_isis_network_type_emulation_6pe_6vpe_config>`  {broadcast|p2p}]
     [:ref:`-igp_isis_router_priority <igp_isis_router_priority_emulation_6pe_6vpe_config>`  <0-127>]
     [:ref:`-igp_isis_area1 <igp_isis_area1_emulation_6pe_6vpe_config>`  <ANY>]
     [:ref:`-igp_isis_area2 <igp_isis_area2_emulation_6pe_6vpe_config>`  <ANY>]
     [:ref:`-igp_isis_area3 <igp_isis_area3_emulation_6pe_6vpe_config>`  <ANY>]
     [:ref:`-igp_isis_circuit_id <igp_isis_circuit_id_emulation_6pe_6vpe_config>`  <0-255>]
     [:ref:`-igp_isis_auth_mode <igp_isis_auth_mode_emulation_6pe_6vpe_config>`  {none|simple|md5}]
     [:ref:`-igp_isis_auth_password <igp_isis_auth_password_emulation_6pe_6vpe_config>`  <ANY>]
     [:ref:`-igp_isis_auth_md5_key <igp_isis_auth_md5_key_emulation_6pe_6vpe_config>`  <0-255>]
     [:ref:`-igp_isis_metric_mode <igp_isis_metric_mode_emulation_6pe_6vpe_config>`  {narrow|wide|narrow_and_wide}]
     [:ref:`-igp_isis_l1_metric <igp_isis_l1_metric_emulation_6pe_6vpe_config>`  <1-63>]
     [:ref:`-igp_isis_l1_wide_metric <igp_isis_l1_wide_metric_emulation_6pe_6vpe_config>`  <0-16777215>]
     [:ref:`-igp_isis_l2_metric <igp_isis_l2_metric_emulation_6pe_6vpe_config>`  <1-63>]
     [:ref:`-igp_isis_l2_wide_metric <igp_isis_l2_wide_metric_emulation_6pe_6vpe_config>`  <0-16777215>]
     [:ref:`-igp_isis_graceful_restart_enable <igp_isis_graceful_restart_enable_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-igp_isis_hello_padding <igp_isis_hello_padding_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-igp_isis_bfd_enable <igp_isis_bfd_enable_emulation_6pe_6vpe_config>`  {true|false}]
 
     MPLS RSVP-TE Router Generation Parameters
     
     [:ref:`-mpls_rsvp_bandwidth_per_link <mpls_rsvp_bandwidth_per_link_emulation_6pe_6vpe_config>`  {1-2147483647}]
     [:ref:`-mpls_rsvp_bandwidth_per_tunnel <mpls_rsvp_bandwidth_per_tunnel_emulation_6pe_6vpe_config>`  {1-2147483647}]
     [:ref:`-mpls_rsvp_egress_label <mpls_rsvp_egress_label_emulation_6pe_6vpe_config>`  {next_available|implicit_null|explicit_null }]
     [:ref:`-mpls_rsvp_transit <mpls_rsvp_transit_emulation_6pe_6vpe_config>`  {accept_all|accept_configured }]
     [:ref:`-mpls_rsvp_min_label <mpls_rsvp_min_label_emulation_6pe_6vpe_config>`  {1-65535}]
     [:ref:`-mpls_rsvp_max_label <mpls_rsvp_max_label_emulation_6pe_6vpe_config>`  {1-65535}]
     [:ref:`-mpls_rsvp_graceful_restart_enable <mpls_rsvp_graceful_restart_enable_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-mpls_rsvp_recover_time <mpls_rsvp_recover_time_emulation_6pe_6vpe_config>`  <0-4294967295>]
     [:ref:`-mpls_rsvp_restart_time <mpls_rsvp_restart_time_emulation_6pe_6vpe_config>`  <0-4294967295>]
     [:ref:`-mpls_rsvp_bfd_enable <mpls_rsvp_bfd_enable_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-mpls_rsvp_request_conf <mpls_rsvp_request_conf_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-mpls_rsvp_hello_enable <mpls_rsvp_hello_enable_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-mpls_rsvp_hello_interval <mpls_rsvp_hello_interval_emulation_6pe_6vpe_config>`  <1-2147483647>]
     [:ref:`-mpls_rsvp_bundle_interval <mpls_rsvp_bundle_interval_emulation_6pe_6vpe_config>`  <1-2147483647>]
     [:ref:`-mpls_rsvp_summary_refresh_interval <mpls_rsvp_summary_refresh_interval_emulation_6pe_6vpe_config>`  <1-2147483647>]
     [:ref:`-mpls_rsvp_inter_packet_delay <mpls_rsvp_inter_packet_delay_emulation_6pe_6vpe_config>`  <1-2147483647>]
     [:ref:`-mpls_rsvp_refresh_interval <mpls_rsvp_refresh_interval_emulation_6pe_6vpe_config>`  <1-2147483647>]
     [:ref:`-mpls_rsvp_refresh_delivery <mpls_rsvp_refresh_delivery_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-mpls_rsvp_retrans_interval <mpls_rsvp_retrans_interval_emulation_6pe_6vpe_config>`  <1-2147483647>]
     [:ref:`-mpls_rsvp_retrans_limit <mpls_rsvp_retrans_limit_emulation_6pe_6vpe_config>`  <0-10>]
     [:ref:`-mpls_rsvp_retrans_delta <mpls_rsvp_retrans_delta_emulation_6pe_6vpe_config>`  <0-3>] 
 
     MPLS LDP Router Generation Parameters
 
     [:ref:`-mpls_ldp_hello_type <mpls_ldp_hello_type_emulation_6pe_6vpe_config>`  { direct|targeted}]
     [:ref:`-mpls_ldp_transport_mode <mpls_ldp_transport_mode_emulation_6pe_6vpe_config>`  { none|tester_ip|router_id }]
     [:ref:`-mpls_ldp_hello_interval <mpls_ldp_hello_interval_emulation_6pe_6vpe_config>`   <1-21845>]
     [:ref:`-mpls_ldp_keepalive_interval <mpls_ldp_keepalive_interval_emulation_6pe_6vpe_config>`   <1-21845>]
     [:ref:`-mpls_ldp_egress_label <mpls_ldp_egress_label_emulation_6pe_6vpe_config>`   { next_available|implicit_null|explicit_null }]
     [:ref:`-mpls_ldp_min_label <mpls_ldp_min_label_emulation_6pe_6vpe_config>`  <1-65535>]
     [:ref:`-mpls_ldp_graceful_restart_enable <mpls_ldp_graceful_restart_enable_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-mpls_ldp_recover_time <mpls_ldp_recover_time_emulation_6pe_6vpe_config>`  <0-4294967>]
     [:ref:`-mpls_ldp_reconnect_time <mpls_ldp_reconnect_time_emulation_6pe_6vpe_config>`  <0-4294967>]
     [:ref:`-mpls_ldp_bfd_enable <mpls_ldp_bfd_enable_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-mpls_ldp_label_adv_mode <mpls_ldp_label_adv_mode_emulation_6pe_6vpe_config>`  {downstream_unsolicited|downstream_on_demand}]
     [:ref:`-mpls_ldp_auth_mode <mpls_ldp_auth_mode_emulation_6pe_6vpe_config>`  {none|md5}]
     [:ref:`-mpls_ldp_auth_password <mpls_ldp_auth_password_emulation_6pe_6vpe_config>`  <ANY>]
 
     MPLS OSPF-SR Router Generation Parameters
 
     [:ref:`-mpls_ospf_sr_algorithms <mpls_ospf_sr_algorithms_emulation_6pe_6vpe_config>`  <0-4294967295>]
     [:ref:`-mpls_ospf_sid_base <mpls_ospf_sid_base_emulation_6pe_6vpe_config>`   <0-4294967295>]
     [:ref:`-mpls_ospf_sid_range <mpls_ospf_sid_range_emulation_6pe_6vpe_config>`   <0-65535>]
     [:ref:`-mpls_ospf_node_sid_index <mpls_ospf_node_sid_index_emulation_6pe_6vpe_config>` <0-4294967295>]
     [:ref:`-mpls_ospf_node_sid_index_step <mpls_ospf_node_sid_index_step_emulation_6pe_6vpe_config>`  <0-4294967295>]
 
     MPLS ISIS-SR Router Generation Parameters
 
     [:ref:`-mpls_isis_sr_algorithm <mpls_isis_sr_algorithm_emulation_6pe_6vpe_config>`  <0-4294967295>]
     [:ref:`-mpls_isis_sid_base <mpls_isis_sid_base_emulation_6pe_6vpe_config>`   <0-4294967295>]
     [:ref:`-mpls_isis_sid_range <mpls_isis_sid_range_emulation_6pe_6vpe_config>`   <0-65535>]
     [:ref:`-mpls_isis_node_sid_index <mpls_isis_node_sid_index_emulation_6pe_6vpe_config>` <0-4294967295>]
     [:ref:`-mpls_isis_node_sid_index_step <mpls_isis_node_sid_index_step_emulation_6pe_6vpe_config>`   <0-4294967295>]
     
     P Router Generation Parameters
 
     [:ref:`-p_router_enable <p_router_enable_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-p_router_num_per_subif <p_router_num_per_subif_emulation_6pe_6vpe_config>` <1-65535>]
     [:ref:`-p_router_topology_type <p_router_topology_type_emulation_6pe_6vpe_config>` {tree|grid}]
     [:ref:`-p_router_id_start <p_router_id_start_emulation_6pe_6vpe_config>` <a.b.c.d>]
     [:ref:`-p_router_id_step <p_router_id_step_emulation_6pe_6vpe_config>` <a.b.c.d>]
     [:ref:`-p_router_ipv4_addr <p_router_ipv4_addr_emulation_6pe_6vpe_config>` <a.b.c.d>]
     [:ref:`-p_router_ipv4_prefix_len <p_router_ipv4_prefix_len_emulation_6pe_6vpe_config>` <0-32>]
 
     PE Router Generation Parameters
 
     [:ref:`-pe_router_num_per_subif <pe_router_num_per_subif_emulation_6pe_6vpe_config>`  <1-10000>]
     [:ref:`-pe_router_id_start <pe_router_id_start_emulation_6pe_6vpe_config>`   <a.b.c.d>]
     [:ref:`-pe_router_id_step <pe_router_id_step_emulation_6pe_6vpe_config>`   <a.b.c.d>]
     [:ref:`-vpn_6vpe_enable <vpn_6vpe_enable_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-bgp_route_reflector_enable <bgp_route_reflector_enable_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-bgp_route_reflector_per_subif <bgp_route_reflector_per_subif_emulation_6pe_6vpe_config>` <1-65535>]
     [:ref:`-bgp_route_reflector_per_pe <bgp_route_reflector_per_pe_emulation_6pe_6vpe_config>` <1-65535>]
     [:ref:`-bgp_route_reflector_id_start <bgp_route_reflector_id_start_emulation_6pe_6vpe_config>` <a.b.c.d>]
     [:ref:`-bgp_route_reflector_id_step <bgp_route_reflector_id_step_emulation_6pe_6vpe_config>` <a.b.c.d>]
     [:ref:`-bgp_route_reflector_cluster_id <bgp_route_reflector_cluster_id_emulation_6pe_6vpe_config>` <a.b.c.d>]
     [:ref:`-bgp_route_reflector_cluster_id_step <bgp_route_reflector_cluster_id_step_emulation_6pe_6vpe_config>` <a.b.c.d>]
     [:ref:`-bgp_route_reflector_ids <bgp_route_reflector_ids_emulation_6pe_6vpe_config>`  <a.b.c.d>]
     [:ref:`-bgp_route_reflector_mode <bgp_route_reflector_mode_emulation_6pe_6vpe_config>`  {stc_as_rr|dut_as_rr}]
     [:ref:`-bgp_bfd_enable <bgp_bfd_enable_emulation_6pe_6vpe_config>` {true|false}]
 
     VPN Generation Parameters
 
     [:ref:`-vrf_count <vrf_count_emulation_6pe_6vpe_config>` <1-65535>]
     [:ref:`-vrf_rd_assignment <vrf_rd_assignment_emulation_6pe_6vpe_config>` {use_rt|manual}]
     [:ref:`-vrf_route_target_start <vrf_route_target_start_emulation_6pe_6vpe_config>` <ANY>]
     [:ref:`-vrf_route_target_step <vrf_route_target_step_emulation_6pe_6vpe_config>` <ANY>]
     [:ref:`-cust_ce_vrf_assignment <cust_ce_vrf_assignment_emulation_6pe_6vpe_config>` {round_robin|sequential}]
     [:ref:`-cust_ce_routing_protocol <cust_ce_routing_protocol_emulation_6pe_6vpe_config>` {bgp|ospf|rip|isis|mixed}]
     [:ref:`-cust_ce_bgp_percent <cust_ce_bgp_percent_emulation_6pe_6vpe_config>` <0-100>]
     [:ref:`-cust_ce_rip_percent <cust_ce_rip_percent_emulation_6pe_6vpe_config>` <0-100>]
     [:ref:`-cust_ce_ospf_percent <cust_ce_ospf_percent_emulation_6pe_6vpe_config>` <0-100>]
     [:ref:`-cust_ce_isis_percent <cust_ce_isis_percent_emulation_6pe_6vpe_config>` <0-100>]
     [:ref:`-cust_ce_bgp_as <cust_ce_bgp_as_emulation_6pe_6vpe_config>` <1-65535>]
     [:ref:`-cust_ce_bgp_as_step_per_ce_enable <cust_ce_bgp_as_step_per_ce_enable_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-cust_ce_bgp_as_step_per_ce <cust_ce_bgp_as_step_per_ce_emulation_6pe_6vpe_config>` <0-65535>]
     [:ref:`-cust_ce_bgp_as_step_per_vrf_enable <cust_ce_bgp_as_step_per_vrf_enable_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-cust_ce_bgp_as_step_per_vrf <cust_ce_bgp_as_step_per_vrf_emulation_6pe_6vpe_config>` <0-65535>]
     [:ref:`-cust_ce_bgp_4byte_as_enable <cust_ce_bgp_4byte_as_enable_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-cust_ce_bgp_4byte_as <cust_ce_bgp_4byte_as_emulation_6pe_6vpe_config>` <ANY>]
     [:ref:`-cust_ce_bgp_4byte_as_step_per_ce_enable <cust_ce_bgp_4byte_as_step_per_ce_enable_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-cust_ce_bgp_4byte_as_step_per_ce <cust_ce_bgp_4byte_as_step_per_ce_emulation_6pe_6vpe_config>` <0-65535>]
     [:ref:`-cust_ce_bgp_4byte_as_step_per_vrf_enable <cust_ce_bgp_4byte_as_step_per_vrf_enable_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-cust_ce_bgp_4byte_as_step_per_vrf <cust_ce_bgp_4byte_as_step_per_vrf_emulation_6pe_6vpe_config>` <0-65535>]
     [:ref:`-cust_rd_start <cust_rd_start_emulation_6pe_6vpe_config>`  <ANY>]
     [:ref:`-cust_rd_step_per_vrf_enable <cust_rd_step_per_vrf_enable_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-cust_rd_step_per_vrf <cust_rd_step_per_vrf_emulation_6pe_6vpe_config>`  <ANY>]
     [:ref:`-cust_rd_step_per_ce_enable <cust_rd_step_per_ce_enable_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-cust_rd_step_per_ce <cust_rd_step_per_ce_emulation_6pe_6vpe_config>`  <ANY>]
      
     [:ref:`-provider_pe_vrf_assignment <provider_pe_vrf_assignment_emulation_6pe_6vpe_config>` {vpn_per_pe|pe_per_vpn}]
     [:ref:`-provider_pe_vrf_count <provider_pe_vrf_count_emulation_6pe_6vpe_config>` <integer>]
     [:ref:`-provider_pe_vrf_all_assign <provider_pe_vrf_all_assign_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-provider_ce_bgp_as_enable <provider_ce_bgp_as_enable_emulation_6pe_6vpe_config>` {true|false}]
     
     [:ref:`-provider_ce_bgp_as <provider_ce_bgp_as_emulation_6pe_6vpe_config>` <1-65535>]
     [:ref:`-provider_ce_bgp_as_step_per_ce_enable <provider_ce_bgp_as_step_per_ce_enable_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-provider_ce_bgp_as_step_per_ce <provider_ce_bgp_as_step_per_ce_emulation_6pe_6vpe_config>` <1-65535>]
     [:ref:`-provider_ce_bgp_as_step_per_vrf_enable <provider_ce_bgp_as_step_per_vrf_enable_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-provider_ce_bgp_as_step_per_vrf <provider_ce_bgp_as_step_per_vrf_emulation_6pe_6vpe_config>` <1-65535>]
     
     [:ref:`-provider_ce_bgp_4byte_as_enable <provider_ce_bgp_4byte_as_enable_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-provider_ce_bgp_4byte_as <provider_ce_bgp_4byte_as_emulation_6pe_6vpe_config>` <ANY>]
     [:ref:`-provider_ce_bgp_4byte_as_step_per_ce_enable <provider_ce_bgp_4byte_as_step_per_ce_enable_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-provider_ce_bgp_4byte_as_step_per_ce <provider_ce_bgp_4byte_as_step_per_ce_emulation_6pe_6vpe_config>` <1-65535>]
     [:ref:`-provider_ce_bgp_4byte_as_step_per_vrf_enable <provider_ce_bgp_4byte_as_step_per_vrf_enable_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-provider_ce_bgp_4byte_as_step_per_vrf <provider_ce_bgp_4byte_as_step_per_vrf_emulation_6pe_6vpe_config>` <1-65535>]
 
     [:ref:`-provider_rd_start <provider_rd_start_emulation_6pe_6vpe_config>`  <ANY>]
     [:ref:`-provider_rd_step_per_vrf_enable <provider_rd_step_per_vrf_enable_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-provider_rd_step_per_vrf <provider_rd_step_per_vrf_emulation_6pe_6vpe_config>`  <ANY>]
     [:ref:`-provider_rd_step_per_ce_enable <provider_rd_step_per_ce_enable_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-provider_rd_step_per_ce <provider_rd_step_per_ce_emulation_6pe_6vpe_config>`  <ANY>]
    
     [:ref:`-cust_ipv6_vpn_route_start <cust_ipv6_vpn_route_start_emulation_6pe_6vpe_config>` <aaaa:bbbb:cccc:dddd:eeee:ffff:gggg:hhhh>]
     [:ref:`-cust_ipv6_vpn_route_step <cust_ipv6_vpn_route_step_emulation_6pe_6vpe_config>` <NUMERIC>]
     [:ref:`-cust_ipv6_vpn_route_prefix_len <cust_ipv6_vpn_route_prefix_len_emulation_6pe_6vpe_config>` <1-128>]
     [:ref:`-cust_ipv6_vpn_route_overlap <cust_ipv6_vpn_route_overlap_emulation_6pe_6vpe_config>`  {true|false}]
     [:ref:`-cust_ipv6_ce_route_type <cust_ipv6_ce_route_type_emulation_6pe_6vpe_config>`  {internal|external}]
     [:ref:`-cust_route_count_per_ce <cust_route_count_per_ce_emulation_6pe_6vpe_config>`   {1-2147483647}]
 
     [:ref:`-provider_ipv6_vpn_route_start <provider_ipv6_vpn_route_start_emulation_6pe_6vpe_config>` <aaaa:bbbb:cccc:dddd:eeee:ffff:gggg:hhhh>]
     [:ref:`-provider_ipv6_vpn_route_step <provider_ipv6_vpn_route_step_emulation_6pe_6vpe_config>` <NUMERIC>]
     [:ref:`-provider_ipv6_vpn_route_prefix_len <provider_ipv6_vpn_route_prefix_len_emulation_6pe_6vpe_config>` <1-128>]
     [:ref:`-provider_ipv6_vpn_route_overlap <provider_ipv6_vpn_route_overlap_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-provider_route_count_per_ce <provider_route_count_per_ce_emulation_6pe_6vpe_config>`   {1-2147483647}]   
     [:ref:`-vrf_route_mpls_label_type <vrf_route_mpls_label_type_emulation_6pe_6vpe_config>` {label_per_site|label_per_route}]
     [:ref:`-vrf_route_mpls_label_start <vrf_route_mpls_label_start_emulation_6pe_6vpe_config>` <1-1048575>]
     
     Traffic Generation Parameters
 
     [:ref:`-traffic_flow_direction <traffic_flow_direction_emulation_6pe_6vpe_config>` {none|fully_meshed|cust_to_core|core_to_customer|bidrectional}]
     [:ref:`-traffic_pattern <traffic_pattern_emulation_6pe_6vpe_config>`  {one_to_one|one_to_many}]
     [:ref:`-traffic_stream_group_method <traffic_stream_group_method_emulation_6pe_6vpe_config>` {aggregate|vpn }]
     [:ref:`-traffic_use_single_stream_per_endpoint_pair <traffic_use_single_stream_per_endpoint_pair_emulation_6pe_6vpe_config>` {true|false}]
     [:ref:`-traffic_load_percent_provider <traffic_load_percent_provider_emulation_6pe_6vpe_config>` <0-100>]
     [:ref:`-traffic_load_percent_cust <traffic_load_percent_cust_emulation_6pe_6vpe_config>` <0-100>]

 
Arguments
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. _handle_emulation_6pe_6vpe_config:

.. option:: -handle

                 Specifies the 6PE/6VPE network configuration handle. This
                 argument is required for -mode delete.

.. _mode_emulation_6pe_6vpe_config:

.. option:: -mode

                 Specifies the action to be performed. This argument is mandatory.
                 Possible values are described below::
                  
                  create   Creates a 6PE/6VPE network configuration
                  
                  delete   Deletes the 6PE/6VPE network configuration specified by
                           -handle

.. _dut_router_id_emulation_6pe_6vpe_config:

.. option:: -dut_router_id

                 Specifies the router ID for the DUT. The value must be in IPv4
                 format. The default value is 10.0.0.1.

.. _dut_as_emulation_6pe_6vpe_config:

.. option:: -dut_as

                 The Autonomous System (AS) number of the DUT. Possible values
                 range from 1 to 65535. The default value is 1.

.. _dut_4byte_as_enable_emulation_6pe_6vpe_config:

.. option:: -dut_4byte_as_enable

                 Enables or disables the 4-byte AS number on the DUT. Possible
                 values are true (enable) and false (disable). The default value
                 is false.
 
.. _dut_4byte_as_emulation_6pe_6vpe_config:

.. option:: -dut_4byte_as

                 Specifies the 4-byte AS number of the DUT, in the format of
                 <integer>:<integer>. The integer must be less than 65535.
                 The default value is 1:1.
 
.. _use_cust_ports_emulation_6pe_6vpe_config:

.. option:: -use_cust_ports

                 Determines whether to set the DUT to port connection for customer
                 ports. Possible values are true and false. Set it to false if the
                 test does not use customer-side ports. The default value is true. 
 
.. _use_provider_ports_emulation_6pe_6vpe_config:

.. option:: -use_provider_ports

                 Determines whether to set the DUT to port connection for provider
                 ports. Possible values are true and false. Set it to false if the
                 test does not use provider-side ports. The default value is true.
 
.. _igp_protocol_emulation_6pe_6vpe_config:

.. option:: -igp_protocol

                 Specifies the Interior Gateway Protocol (IGP) to be used by the
                 DUT. Possible values are::
                 
                  OSPF     OSPF
                  ISIS     ISIS
                  RIP      RIP
                  NONE     No IGP protocol
                  
                 The default value is OSPF.

.. _mpls_protocol_emulation_6pe_6vpe_config:

.. option:: -mpls_protocol

                 Specifies the MPLS protocol to be used by the DUT. Possible
                 values are::
                 
                  NONE     No MPLS protocol
                  LDP      LDP
                  RSVP     RSVP-TE
                  OSPF     OSPF SR
                  ISIS     ISIS SR
                  
                 The default value is LDP.
 
.. _igp_ospf_area_id_emulation_6pe_6vpe_config:

.. option:: -igp_ospf_area_id

                 Specifies the IP address that indicates the customer-side area to
                 which the emulated router belongs. The default value is 0.0.0.0.
                 This argument is available when -igp_protocol is set to OSPF.
 
.. _igp_ospf_network_type_emulation_6pe_6vpe_config:

.. option:: -igp_ospf_network_type

                 Specifies the network link type to use.   
                 Possible values are::
                  
                  native      Use the adjacency specified by the port-type
                  
                  broadcast   Use a Broadcast adjacency
                  
                  p2p         Use a P2P adjacency
                  
                 The default value is native. This argument is available when
                 -igp_protocol is set to OSPF.

.. _igp_ospf_router_priority_emulation_6pe_6vpe_config:

.. option:: -igp_ospf_router_priority

                 Specifies the router priority of the emulated router. Possible
                 values range from 0 to 255. The default value is 0. This argument
                 is available when -igp_protocol is set to OSPF.

.. _igp_ospf_interface_cost_emulation_6pe_6vpe_config:

.. option:: -igp_ospf_interface_cost

                 Specifies the cost of the interface connecting the emulated
                 router to the neighbor DUT router. Possible values range from 1
                 to 65535. The default value is 1. This argument is available when
                 -igp_protocol is set to OSPF.

.. _igp_ospf_options_emulation_6pe_6vpe_config:

.. option:: -igp_ospf_options

                 Specifies the Options field that describes the optional OSPF
                 capabilities of the router. Possible values range from 0 to 0x7f.
                 The values are described below::
                 
                  tbit      Type of Service (TOS) (T,0).
                  ebit      Specifies the way AS-external-LSAs are flooded (E,1)
                  mcbit     Specifies whether IP multicast datagrams are forwarded (MC,2)
                  npbit     Specifies the handling of Type-7 LSAs (NSSA) (N/P,3)
                  eabit     Specifies the router's willingness to receive and
                            forward External-Attributes-LSAs (EA,4)
                  dcbit     Specifies the router's handling of demand circuits (DC,5)
                  obit      Specifies the router's willingness to receive and forward
                            Opaque LSAs as specified in RFC 2370 (O,6)
                  unused7   This bit is not used
                 
                 The default for OSPFv2 is 0x02, which sets the E-bit.

.. _igp_ospf_auth_mode_emulation_6pe_6vpe_config:

.. option:: -igp_ospf_auth_mode

                 Specifies the type of OSPFv2 authentication to be used. 
                 Possible values are::
                 
                  none     No authentication
                  simple   Use simple authentication
                  md5      Use MD5 authentication
                  
                 The default value is none. This argument is available when
                 -igp_protocol is set to OSPF.

.. _igp_ospf_auth_password_emulation_6pe_6vpe_config:

.. option:: -igp_ospf_auth_password

                 Specifies the password used for OSPFv2 authentication. This
                 argument is available when -igp_ospf_auth_mode is set to simple
                 or md5. When you specify -igp_ospf_auth_mode simple, the value
                 must be of 1-8 alphanumeric characters. When you specify
                 -igp_ospf_auth_mode md5, the value must be of 1-16 alphanumeric
                 characters. The default value is "spirent".

.. _igp_ospf_auth_md5_key_emulation_6pe_6vpe_config:

.. option:: -igp_ospf_auth_md5_key

                 Specifies the MD5 key used for OSPFv2 authentication. Possible
                 values range from 0 to 255. The default value is 1. This argument
                 is available when -igp_ospf_auth_mode is set to md5.

.. _igp_ospf_graceful_restart_enable_emulation_6pe_6vpe_config:

.. option:: -igp_ospf_graceful_restart_enable

                 Enables or disables graceful restart for OSPF sessions. Possible
                 values are true (enable) and false (disable). The default value
                 is false. This argument is available when -igp_protocol is set to
                 OSPF.

.. _igp_ospf_graceful_restart_type_emulation_6pe_6vpe_config:

.. option:: -igp_ospf_graceful_restart_type

                 Specifies the type of graceful restart to be used by the OSPF
                 session. Possible values are::
                 
                   none              No graceful restart
                   rfc_standard      RFC3623
                   ll_signalling     Link-Layer Signaling
                   
                  The default value is none.

.. _igp_ospf_bfd_enable_emulation_6pe_6vpe_config:

.. option:: -igp_ospf_bfd_enable

                 Enables or disables Bidirectional Forwarding Detection (BFD) on
                 the OSPF interface. Possible values are true (enable) and false
                 (disable). The default value is false. This argument is available
                 when -igp_protocol is set to OSPF.

.. _igp_isis_level_emulation_6pe_6vpe_config:

.. option:: -igp_isis_level

                 Specifies the IS-IS level to be used on the customer side. It
                 defines the type of adjacency that Spirent HLTAPI establishes
                 with the DUT. Possible values are described below::
                 
                  level1             Level 1 (intra-area)
                  level2             Level 2 (inter-area)
                  level1_and_2       Both Level 1 and Level 2
                  
                 The default value is level2. This argument is available when
                 -igp_protocol is set to ISIS. 

.. _igp_isis_network_type_emulation_6pe_6vpe_config:

.. option:: -igp_isis_network_type

                 Specifies the IS-IS network type on the customer side. Possible
                 values are::
                 
                  broadcast     Broadcast network 
                  p2p           P2P network
                  
                 The default value is broadcast. This argument is available when
                 -igp_protocol is set to ISIS.

.. _igp_isis_router_priority_emulation_6pe_6vpe_config:

.. option:: -igp_isis_router_priority

                 Specifies the priority for the emulated IS-IS router. Possible
                 values range from 0 to 127. The default value is 0. This argument
                 is available when -igp_protocol is set to ISIS.

.. _igp_isis_area1_emulation_6pe_6vpe_config:

.. option:: -igp_isis_area1

                 Specifies the mandatory area address 1. You must specify at least
                 one address. Spirent HLTAPI supports up to three addresses per
                 emulated router. This argument is available when -igp_protocol is
                 set to ISIS.

.. _igp_isis_area2_emulation_6pe_6vpe_config:

.. option:: -igp_isis_area2

                 Specifies the optional area address 2. This argument is available
                 when -igp_protocol is set to ISIS. The default value is "".

.. _igp_isis_area3_emulation_6pe_6vpe_config:

.. option:: -igp_isis_area3

                 Specifies the optional area address 3. This argument is available
                 when -igp_protocol is set to ISIS. The default value is "".

.. _igp_isis_circuit_id_emulation_6pe_6vpe_config:

.. option:: -igp_isis_circuit_id

                 Specifies the circuit ID for the IS-IS session. Possible values
                 range from 0 to 255. The default value is 1. This argument is
                 available when -igp_protocol is set to ISIS.

.. _igp_isis_auth_mode_emulation_6pe_6vpe_config:

.. option:: -igp_isis_auth_mode

                 Specifies the type of IS-IS authentication to be used. Possible
                 values are::
                 
                   none      No authentication
                   simple    Use simple authentication
                   md5       Use the MD5 key ID 
                   
                 The default value is none. This argument is available when
                 -igp_protocol is set to ISIS.
                  
.. _igp_isis_auth_password_emulation_6pe_6vpe_config:

.. option:: -igp_isis_auth_password

                 Specifies the password used for IS-IS authentication. This
                 argument is available when -igp_isis_auth_mode is set to simple
                 or md5. When you specify -igp_isis_auth_mode simple, the value
                 must be of 1-8 alphanumeric characters. When you specify
                 -igp_isis_auth_mode md5, the value must be of 1-16 alphanumeric
                 characters. The default value is "spirent".

.. _igp_isis_auth_md5_key_emulation_6pe_6vpe_config:

.. option:: -igp_isis_auth_md5_key

                 Specifies the MD5 key used in IS-IS authentication. Possible
                 values range from 0 to 255. The default value is 1. This argument
                 is available when -igp_isis_auth_mode is set to md5.

.. _igp_isis_metric_mode_emulation_6pe_6vpe_config:

.. option:: -igp_isis_metric_mode

                 Specifies the length of the metric field in the Link State Path
                 (LSP) packet. This argument is available when -igp_protocol is
                 set to ISIS. Possible values are described below::
                 
                  narrow             Router advertises routes with a
                                     narrow (6-bit) metric
                  wide               Router advertises routes with a wide
                                    (24 or 32-bit) metric (required for IS-IS TE)
                  narrow_and_wide    Router advertises the same route with both
                                     metrics
                                     
                 The default value is narrow_and_wide.

.. _igp_isis_l1_metric_emulation_6pe_6vpe_config:

.. option:: -igp_isis_l1_metric

                 Specifies the metric of the emulated router interface. It is
                 blank and disabled if -igp_isis_level is set to level2 or if
                 -igp_isis_metric_mode is set to wide. Possible values range from
                 1 to 63. The default value is 1. 
 
.. _igp_isis_l1_wide_metric_emulation_6pe_6vpe_config:

.. option:: -igp_isis_l1_wide_metric

                 Indicates the 3-octet metric of a link from the emulated ISIS
                 router to the DUT. It is blank and disabled if -igp_isis_level is
                 set to level2 or if -igp_isis_metric_mode is set to narrow.
                 Possible values range from 0 to 16777215. The default value is 1.

.. _igp_isis_l2_metric_emulation_6pe_6vpe_config:

.. option:: -igp_isis_l2_metric

                 Indicates the metric of the emulated ISIS router interface. It is
                 blank and disabled if -igp_isis_level is set to level1 or if
                 -igp_isis_metric_mode is set to wide. Possible values range from
                 1 to 63. The default value is 1.

.. _igp_isis_l2_wide_metric_emulation_6pe_6vpe_config:

.. option:: -igp_isis_l2_wide_metric

                 Indicates the 3-octet traffic engineering metric of a link from
                 the emulated ISIS router to the DUT. It is blank and disabled if
                 -igp_isis_level is set to level1 or if -igp_isis_metric_mode is
                 set to narrow. Possible values range from 0 to 16777215. The
                 default is 1.

.. _igp_isis_graceful_restart_enable_emulation_6pe_6vpe_config:

.. option:: -igp_isis_graceful_restart_enable

                 Enables or disables the IS-IS graceful restart. Possible values
                 are false (disable) and true (enable). The default value is
                 false.

.. _igp_isis_hello_padding_emulation_6pe_6vpe_config:

.. option:: -igp_isis_hello_padding

                 Enables or disables Hello padding for IS-IS sessions. Possible
                 values are true (enable) and false (disable). The default value
                 is true. This argument is available when you specify
                 -igp_protocol ISIS. 

.. _igp_isis_bfd_enable_emulation_6pe_6vpe_config:

.. option:: -igp_isis_bfd_enable

                 Enables or disables BFD on IS-IS interfaces. Possible values are
                 true (enable) and false (disable). The default value is false. 

.. _mpls_rsvp_bandwidth_per_link_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_bandwidth_per_link

                 Specifies the maximum bandwidth per ISIS/OSPFv2 TE link, in bytes
                 per second, for simulated provider router topology links.
                 Possible values range from 1 to 2147483647. The default value is
                 100000. This argument is available when you specify
                 -mpls_protocol RSVP.

.. _mpls_rsvp_bandwidth_per_tunnel_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_bandwidth_per_tunnel

                 Specifies the RSVP-TE bandwidth rate, in bytes per second, for
                 provider tunnels. Possible values range from 1 to 2147483647. The
                 default value is 0. This argument is available when you specify
                 -mpls_protocol RSVP.

.. _mpls_rsvp_egress_label_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_egress_label

                 Specifies the label to be advertised when emulated router is at the
                 tail-end of the tunnel. This argument is available when you
                 specify -mpls_protocol rsvp. The values are described below::
                  
                  next_available     Advertises the next available label
                  
                  implicit_null      Advertises label 3, the implicit null label
                  
                  explicit_null      Advertise label 9, the explicit null label
                  
                 The default value is next_available.

.. _mpls_rsvp_transit_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_transit

                 Defines the RESV message sent when emulated router is not the
                 tail-end router for PATH messages it receives. This argument is
                 available when you specify -mpls_protocol rsvp. Possible values
                 are described below::
                  
                  accept_all         The router sends an RESV message with
                                     the next available label for every PATH
                                     message received by the unique MAC/VLAN
                                     combination on the port
                                     
                  accept_configured  The router sends an RESV message with
                                     the next available label in response to PATH
                                     messages that match one of its egress
                                     tunnels
                                     
                 The default value is accept_configured.                                 
                                     
.. _mpls_rsvp_min_label_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_min_label

                 Defines the minimum label number used by the RSVP session.
                 Possible values range from 1 to 65535. The default value is 16.
                 This argument is available when you specify -mpls_protocol RSVP.

.. _mpls_rsvp_max_label_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_max_label

                 Defines the maximum label number used by the RSVP session.
                 Possible values range from 1 to 65535. The default value is
                 65535. This argument is available when you specify -mpls_protocol
                 RSVP.

.. _mpls_rsvp_graceful_restart_enable_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_graceful_restart_enable

                 Enables or disables graceful restart for RSVP. Possible values
                 are false (disable) and true (enable).  The default value is false.  

.. _mpls_rsvp_recover_time_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_recover_time

                 Specifies the length of time (in milliseconds) that the sender
                 wants the recipient to re-synchronize RSVP and MPLS forwarding
                 state with the sender, after the re-establishment of Hello
                 synchronization. Possible values range from 0 to 4294967295. The
                 default value is 0. This argument is available when
                 -mpls_rsvp_graceful_restart_enable is set to true.

.. _mpls_rsvp_restart_time_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_restart_time

                 Specifies the amount of time (in milliseconds) it takes the
                 sender of the object to restart its RSVP component and the
                 communication channel used for RSVP communication. Possible
                 values are 0 to 4294967295. The default value is 3000. This
                 argument is available when -mpls_rsvp_graceful_restart_enable is
                 set to true.

.. _mpls_rsvp_bfd_enable_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_bfd_enable

                 Enables or disables BFD on RSVP interfaces. Possible values are
                 true (enable) and false (disable). The default value is false. 
 
.. _mpls_rsvp_request_conf_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_request_conf

                 Determines whether to include an RESV_CONFIRM object in the RESV
                 message. Possible values are true and false. When it is set to
                 true, an RESV_CONFIRM object will be included in the RESV
                 message. The default value is false.
 
.. _mpls_rsvp_hello_enable_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_hello_enable

                 Enables or disables Hello packets for RSVP sessions. Possible
                 values are true (enable) and false (disable). The default value is
                 false.
 
.. _mpls_rsvp_hello_interval_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_hello_interval

                 Specifies the interval between RSVP Hello packets. Possible
                 values range from 1 to 2147483647. The default value is 1000.
                 This argument is available when -mpls_rsvp_hello_enable is set to
                 true.

.. _mpls_rsvp_bundle_interval_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_bundle_interval

                 Specifies the time interval (in milliseconds) to wait before
                 sending queued messages. Messages are held in a buffer and are
                 sent out as a bundle after the interval (in ms) expires or when
                 message size exceeds the MTU. Possible values range from 1 to
                 2147483647. The default value is 1000.

.. _mpls_rsvp_summary_refresh_interval_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_summary_refresh_interval

                 Specifies the time interval (in milliseconds) to gather refresh
                 messages that would have been sent out individually. Possible
                 values range from 1 to 2147483647. The default value is 9000.

.. _mpls_rsvp_inter_packet_delay_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_inter_packet_delay

                 Specifies the time delay (in milliseconds) between transmitted
                 RSVP packets. Possible values range from 0 to 2147483647. The
                 default value is 30.

.. _mpls_rsvp_refresh_interval_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_refresh_interval

                 Specifies the time interval for a PATH and RESV message to be
                 sent out to the path receiver to refresh the PATH/RESV state
                 along each hop of the path. Possible values range from 1 to
                 2147483647. The default value is 30000.

.. _mpls_rsvp_refresh_delivery_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_refresh_delivery

                 Enables or disables reliable delivery for RSVP sessions. Possible
                 values are true (enable) and false (disable). The default value is
                 false.
              
.. _mpls_rsvp_retrans_interval_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_retrans_interval

                 Specifies the initial retransmission interval (in milliseconds)
                 for unacknowledged messages. Possible values range from 1 to
                 2147483647. The default value is 500.

.. _mpls_rsvp_retrans_limit_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_retrans_limit

                 Specifies the maximum number of times a message is transmitted
                 without being acknowledged. Possible values range from 0 to 10.
                 The default value is 3.

.. _mpls_rsvp_retrans_delta_emulation_6pe_6vpe_config:

.. option:: -mpls_rsvp_retrans_delta

                 Specifies the multiplier by which the retransmission interval is
                 increased each time an unacknowledged message is retransmitted.
                 Possible values range from 0 to 3. The default value is 1.

.. _mpls_ldp_hello_type_emulation_6pe_6vpe_config:

.. option:: -mpls_ldp_hello_type

                 Specifies the type of Hello packets for LDP. Possible values are::
                 
                  direct    The Peer IP address is the DUT interface address.
                            Used to locate directly connected neighbors.
                           
                  targeted  The Peer IP address is the DUT loopback address.
                            Used to locate neighbors which are not directly connected.
                           
                 This argument is available when you specify -mpls_protocol LDP.

.. _mpls_ldp_transport_mode_emulation_6pe_6vpe_config:

.. option:: -mpls_ldp_transport_mode

                 Specifies the mode of the LDP Transport Address TLV. Possible
                 values are::
                 
                  none          The Transport Address TLV will not be included in
                                LDP Hello messages
                                
                  tester_ip     The LSR will take the emulated router interface
                                address as the transport address and include
                                the Transport Address TLV in LDP Hello messages
                                
                  router_id     The LSR will take the emulated router ID, that is,
                                the loopback address as the transport address and
                                include the Transport Address TLV in LDP Hello
                                messages.
                                
                 The default value is tester_ip. This argument is available when
                 you specify -mpls_protocol LDP.
 
.. _mpls_ldp_hello_interval_emulation_6pe_6vpe_config:

.. option:: -mpls_ldp_hello_interval

                 Specifies the amount of time, in seconds, between Hello messages
                 in an LDP session. Possible values range from 1 to 21845. The
                 default value is 5. This argument is available when you specify
                 -mpls_protocol LDP.

.. _mpls_ldp_keepalive_interval_emulation_6pe_6vpe_config:

.. option:: -mpls_ldp_keepalive_interval

                 Specifies the amount of time, in seconds, between KEEPALIVE
                 messages. Possible values range from 1 to 21845. The default value is
                 60. This argument is available when you specify -mpls_protocol
                 LDP.

.. _mpls_ldp_egress_label_emulation_6pe_6vpe_config:

.. option:: -mpls_ldp_egress_label

                 Specifies the emulated label to be advertised by the emulated peer.
                 Possible values are described below::
                 
                  next_available     Advertises the next available label
                  implicit_null      Advertises label 3, the implicit null label
                  explicit_null      Advertise label 9, the explicit null label
                  
                 The default value is next_available. This argument is available when
                 you specify -mpls_protocol LDP. 
 
.. _mpls_ldp_min_label_emulation_6pe_6vpe_config:

.. option:: -mpls_ldp_min_label

                 Defines the minimum label number used by the LDP session.
                 Possible values range from 1 to 65535. The default value is 16.
                 This argument is available when you specify -mpls_protocol LDP.

.. _mpls_ldp_graceful_restart_enable_emulation_6pe_6vpe_config:

.. option:: -mpls_ldp_graceful_restart_enable

                 Enables or disables graceful restart for LDP sessions. Possible
                 values are true (enable) and false (disable). The default value
                 is false. This argument is available when you specify
                 -mpls_protocol LDP.

.. _mpls_ldp_recover_time_emulation_6pe_6vpe_config:

.. option:: -mpls_ldp_recover_time

                 Specifies the length of time (in milliseconds) that the sender
                 desires for the recipient to re-synchronize LDP and MPLS
                 forwarding state with the sender, after the re-establishment of
                 Hello synchronization. Possible values are 0 to 4294967. The
                 default value is 140. This argument is available when
                 -mpls_ldp_graceful_restart_enable is set to true.

.. _mpls_ldp_reconnect_time_emulation_6pe_6vpe_config:

.. option:: -mpls_ldp_reconnect_time

                 Specifies the amount of time, in seconds, it takes Spirent HLTAPI
                 to reconnect after a graceful restart. To use this argument, you
                 must set -mpls_ldp_graceful_restart_enable to true and specify a
                 value for the -mpls_ldp_recover_time argument. Possible values
                 range from 0 to 4294967. The default value is 60.

.. _mpls_ldp_bfd_enable_emulation_6pe_6vpe_config:

.. option:: -mpls_ldp_bfd_enable

                 Enables or disables BFD on LDP interfaces. Possible values are
                 true (enable) and false (disable). The default value is false.
                 This argument is available when -mpls_protocol is set to LDP.

.. _mpls_ldp_label_adv_mode_emulation_6pe_6vpe_config:

.. option:: -mpls_ldp_label_adv_mode

                 Specifies the label advertisement mode for LDP sessions.
                 Possible values are downstream_unsolicited and
                 downstream_on_demand. The default value is downstream_on_demand.
                 
.. _mpls_ldp_auth_mode_emulation_6pe_6vpe_config:

.. option:: -mpls_ldp_auth_mode

                 Specifies the authentication type for LDP.
                 Possible values are::
                 
                  none     No authentication  
                  md5       MD5 authentication
                  
                 The default value is none.

.. _mpls_ldp_auth_password_emulation_6pe_6vpe_config:

.. option:: -mpls_ldp_auth_password

                 Specifies the password used for LDP authentication. This
                 argument is available when -mpls_ldp_auth_mode is set to md5.
                 The default value is "Spirent".

.. _mpls_ospf_sr_algorithms_emulation_6pe_6vpe_config:

.. option:: -mpls_ospf_sr_algorithms

                 A comma-separated list of integers to specify the algorithm to
                 calculate the reachability to other nodes or to prefixes attached
                 to these nodes. Possible values range from 0 to 255. The default
                 value is 0. This argument is available when -mpls_protocol is set
                 to OSPF.
 
.. _mpls_ospf_sid_base_emulation_6pe_6vpe_config:

.. option:: -mpls_ospf_sid_base

                 Specifies the base value for the SID/Label range. Possible values
                 range from 0 to 4294967295. The default value is 100. This
                 argument is available when -mpls_protocol is set to OSPF.
 
.. _mpls_ospf_sid_range_emulation_6pe_6vpe_config:

.. option:: -mpls_ospf_sid_range

                 Specifies the size of the SID/Label range for OSPF SR. Possible
                 values range from 0 to 65535. The default value is 100.  This
                 argument is available when -mpls_protocol is set to OSPF.
 
.. _mpls_ospf_node_sid_index_emulation_6pe_6vpe_config:

.. option:: -mpls_ospf_node_sid_index

                 Specifies the index value for the SID sub-TLV of OSPF SR.
                 Possible values range from 0 to 4294967295. The default value is
                 0. This argument is available when -mpls_protocol is set to OSPF.
 
.. _mpls_ospf_node_sid_index_step_emulation_6pe_6vpe_config:

.. option:: -mpls_ospf_node_sid_index_step

                 Specifies the increment value with which to create subsequent SID
                 indexes of ISIS SR. Possible values range from 0 to
                 4294967295. The default value is 1. This argument is available
                 when -mpls_protocol is set to OSPF.

.. _mpls_isis_sr_algorithm_emulation_6pe_6vpe_config:

.. option:: -mpls_isis_sr_algorithm

                 Specifies the ISIS SR algorithm, in string format. The default
                 value is 0. This argument is available when -mpls_protocol is set
                 to ISIS.
 
.. _mpls_isis_sid_base_emulation_6pe_6vpe_config:

.. option:: -mpls_isis_sid_base

                 Specifies the base value for the SID/Label range of OSPF SR.
                 Possible values range from 0 to 4294967295. The default value is
                 100. This argument is available when -mpls_protocol is set to
                 ISIS.
 
.. _mpls_isis_sid_range_emulation_6pe_6vpe_config:

.. option:: -mpls_isis_sid_range

                 Specifies the size of the SID/Label range for OSPF SR. 
                 Possible values range from 0 to 65535. The default value is 100.
                 This argument is available when -mpls_protocol is set to ISIS.
                 
.. _mpls_isis_node_sid_index_emulation_6pe_6vpe_config:

.. option:: -mpls_isis_node_sid_index

                 Specifies the index value for the SID sub-TLV of ISIS SR.  
                 Possible values range from 0 to 4294967295. The default value is
                 0.  This argument is available when -mpls_protocol is set to ISIS.
 
.. _mpls_isis_node_sid_index_step_emulation_6pe_6vpe_config:

.. option:: -mpls_isis_node_sid_index_step

                 Specifies the increment value with which to create subsequent SID
                 indexes of the ISIS SR. Possible values range from 0 to
                 4294967295. The default value is 1. This argument is available when 
                 -mpls_protocolo is set to ISIS.

.. _p_router_enable_emulation_6pe_6vpe_config:

.. option:: -p_router_enable

                 Enables or disables the emulation of provider (P) routers in the
                 test. Possible values are true and false. When it is set to
                 false, only provider edge routers will be emulated or simulated.
                 The default value is true.

.. _p_router_num_per_subif_emulation_6pe_6vpe_config:

.. option:: -p_router_num_per_subif

                 Specifies the number of P routers per sub-interface on the
                 provider side. Only one emulated P router can be created per
                 sub-interface. If this number is greater than 1, the additional P
                 routers are simulated through the IGP protocol routes. The
                 topology for the additional P routers is determined by the
                 -p_router_topology_type option. Possible values range from 1 to
                 65535. The default value is 1. This argument is available when
                 -p_router_enable is set to true.
 
.. _p_router_topology_type_emulation_6pe_6vpe_config:

.. option:: -p_router_topology_type

                 Defines the topology of the provider network. Possible
                 values are tree and grid. The default value is tree. 
 
.. _p_router_id_start_emulation_6pe_6vpe_config:

.. option:: -p_router_id_start

                 Defines the first loopback address of emulated P routers. The
                 value must be in IPv4 format. The default value is 192.0.1.1.
                 This argument is available when -p_router_enable is set to true.
 
.. _p_router_id_step_emulation_6pe_6vpe_config:

.. option:: -p_router_id_step

                 Specifies the step value by which to generate additional loopback
                 addresses for the emulated P routers. The value must be in IPv4
                 format. The default value is 0.0.1.0. This argument is available
                 when -p_router_enable is set to true.
 
.. _p_router_ipv4_addr_emulation_6pe_6vpe_config:

.. option:: -p_router_ipv4_addr

                 Specifies the starting IPv4 interface address of the emulated P
                 routers. The default value is 1.0.0.1. This argument is available
                 when -p_router_enable is set to true.
 
.. _p_router_ipv4_prefix_len_emulation_6pe_6vpe_config:

.. option:: -p_router_ipv4_prefix_len

                 Specifies the IP prefix length on the simulated P router.
                 Possible values range from 0 to 32. The default value is 24. This
                 argument is available when -p_router_enable is set to true.

.. _pe_router_num_per_subif_emulation_6pe_6vpe_config:

.. option:: -pe_router_num_per_subif

                 Defines the number of PE routers created on each
                 provider sub-interface. Possible values range from 1 to
                 65535. The default value is 1. This argument is available when
                 -p_router_enable is set to true.
 
.. _pe_router_id_start_emulation_6pe_6vpe_config:

.. option:: -pe_router_id_start

                 Specifies the starting IPv4 address for the PE router. The
                 default is 10.0.0.2. This argument is available when
                 -p_router_enable is set to true.
 
.. _pe_router_id_step_emulation_6pe_6vpe_config:

.. option:: -pe_router_id_step

                 Defines the step size by which the provider-side PE router is
                 incremented. The default value is 0.0.0.1. This argument is
                 available when -p_router_enable is set to true.
 
.. _vpn_6vpe_enable_emulation_6pe_6vpe_config:

.. option:: -vpn_6vpe_enable

                 Determines whether to use 6PE or 6VPE in the test. Possible
                 values are true (6VPE) and false (6PE). The default value is
                 false.

.. _bgp_route_reflector_enable_emulation_6pe_6vpe_config:

.. option:: -bgp_route_reflector_enable

                 Enables or disables route reflectors on the core side. Possible
                 values are true (enable) and false (disable). The default value
                 is false.

.. _bgp_route_reflector_per_subif_emulation_6pe_6vpe_config:

.. option:: -bgp_route_reflector_per_subif

                 Specifies the number of route reflectors per provider
                 sub-interface. Possible values range from 1 to 65535. The default
                 is 1. This argument is available when -bgp_route_reflector_enable
                 is set to true.

.. _bgp_route_reflector_per_pe_emulation_6pe_6vpe_config:

.. option:: -bgp_route_reflector_per_pe

                 Specifies the number of route reflectors per PE router. Possible
                 values range from 0 to 65535. The default value is 1. This
                 argument is available when -bgp_route_reflector_enable is set to
                 true.

.. _bgp_route_reflector_id_start_emulation_6pe_6vpe_config:

.. option:: -bgp_route_reflector_id_start

                 Specifies the starting loopback IPv4 address of route reflectors.
                 The default value is 7.7.7.7. This argument is available when
                 -bgp_route_reflector_enable is set to true.

.. _bgp_route_reflector_id_step_emulation_6pe_6vpe_config:

.. option:: -bgp_route_reflector_id_step

                 The amount by which to increment the loopback IP address
                 (-bgp_route_reflector_loopback_ipv4_addr) for each subsequent
                 route reflector. The value must be in IPv4 format. The default
                 value is 0.0.0.1. This argument is available when
                 -bgp_route_reflector_enable is set to true.

.. _bgp_route_reflector_cluster_id_emulation_6pe_6vpe_config:

.. option:: -bgp_route_reflector_cluster_id

                 Specifies the starting cluster ID for route reflectors. This
                 ID enables route reflectors to recognize route updates from route
                 reflectors in the same cluster. The default value is 0.0.0.0.
                 This argument is available when -bgp_route_reflector_enable is
                 set to true.

.. _bgp_route_reflector_cluster_id_step_emulation_6pe_6vpe_config:

.. option:: -bgp_route_reflector_cluster_id_step

                 The amount by which to increment the cluster ID
                 (-bgp_route_reflector_cluster_id) for each subsequent route
                 reflector. The default value is 0.0.0.1. This argument is
                 available when -mpls_protocol is set to BGP.

.. _bgp_route_reflector_ids_emulation_6pe_6vpe_config:

.. option:: -bgp_route_reflector_ids

                 Specifies the BGP route reflector ID. The value must be in IPv4
                 format. The default value is 0.0.0.0.

.. _bgp_route_reflector_mode_emulation_6pe_6vpe_config:

.. option:: -bgp_route_reflector_mode

                 Specifies the BGP reflector mode. Possible values are::
                 
                  dut_as_rr   Specify the DUT as the route reflector
                  stc_as_rr   Specify Spirent TestCenter as the route reflector
                  
                 The default value is stc_as_rr. This argument is available when
                 -mpls_protocol is set to BGP.

.. _bgp_bfd_enable_emulation_6pe_6vpe_config:

.. option:: -bgp_bfd_enable

                 Enables or disables BFD on BGP interfaces. Possible values are
                 true (enable) and false (disable). The default value is false.
                 This argument is available when -mpls_protocol is set to BGP.

.. _vrf_count_emulation_6pe_6vpe_config:

.. option:: -vrf_count

                 Specifies the number of VPN Routing and Forwarding tables (VRFs)
                 to be configured. Possible values range from 1 to 65535. The
                 default is 1.

.. _vrf_rd_assignment_emulation_6pe_6vpe_config:

.. option:: -vrf_rd_assignment

                 Specifies the route distinguisher assignment mode. Possible
                 values are::
                 
                  use_rt   Use the route target field for all
                           route distinguishers in the VPN
                           
                  manual   Manually configure route distinguishers 
                  
                 The default value is use_rt.

.. _vrf_route_target_start_emulation_6pe_6vpe_config:

.. option:: -vrf_route_target_start

                 Specifies the starting route target for the VPN, in the format of
                 AS-Number:Value or IPv4-Address:Value. The default value is 1:00.

.. _vrf_route_target_step_emulation_6pe_6vpe_config:

.. option:: -vrf_route_target_step

                 Specifies the step size by which the route target is incremented.
                 The value must be in the format of AS-Number:Value or
                 IPv4-Address:Value. The default value is 1:00.

.. _cust_ce_vrf_assignment_emulation_6pe_6vpe_config:

.. option:: -cust_ce_vrf_assignment

                 Determines how VRFs are assigned to CE routers on the customer
                 side. Possible values are::
                 
                  round_robin        The first CE created is assigned to
                                     the first VRF. The second CE created
                                     is assigned to the second VRF, and so forth.
                                     When the specified number of VRFs is reached,
                                     the VRF assignment repeats from the first
                                     VRF.
                                     
                  sequential         CEs created are assigned to the
                                     first VRF until the calculated number of CEs
                                     per VRF is reached. Additional CEs are
                                     assigned to the second and subsequent VRFs in
                                     the same fashion.

.. _cust_ce_routing_protocol_emulation_6pe_6vpe_config:

.. option:: -cust_ce_routing_protocol

                 Defines the interior gateway routing protocol to be used by CEs
                 on the customer side. Possible values are bgp, ospf, rip, isis,
                 and mixed. The default value is bgp. 
 
.. _cust_ce_bgp_percent_emulation_6pe_6vpe_config:

.. option:: -cust_ce_bgp_percent

                 Specifies the percentage of customer-side CEs using BGP. This
                 argument is available when -cust_ce_routing_protocol
                 is set to mixed. Possible values range from 0 to 100. The default
                 value is 0.
 
.. _cust_ce_rip_percent_emulation_6pe_6vpe_config:

.. option:: -cust_ce_rip_percent

                 Specifies the percentage of customer-side CEs using RIP. This
                 argument is available when -cust_ce_routing_protocol is set to
                 mixed. Possible values range from 0 to 100. The default value is
                 0.
 
.. _cust_ce_ospf_percent_emulation_6pe_6vpe_config:

.. option:: -cust_ce_ospf_percent

                 Specifies the percentage of customer-side CEs using OSPFv2. This
                 argument is available when -cust_ce_routing_protocol is set to
                 mixed. Possible values range from 0 to 100. The default value is
                 0.

.. _cust_ce_isis_percent_emulation_6pe_6vpe_config:

.. option:: -cust_ce_isis_percent

                 Specifies the percentage of customer-side CEs using IS-IS. This
                 argument is available when -cust_ce_routing_protocol is set to
                 mixed. Possible values range from 0 to 100. The default value is
                 0.

.. _cust_ce_bgp_as_emulation_6pe_6vpe_config:

.. option:: -cust_ce_bgp_as

                 Specifies the starting BGP AS number on the customer side.
                 Possible values range from 1 to 65535. The default value is 1.

.. _cust_ce_bgp_as_step_per_ce_enable_emulation_6pe_6vpe_config:

.. option:: -cust_ce_bgp_as_step_per_ce_enable

                 Enables or disables the step value for additional AS numbers
                 across CE routers on the customer side. Possible values are true
                 and false. The default value is false. This argument is available
                 when -cust_ce_routing_protocol is set to BGP or mixed.

.. _cust_ce_bgp_as_step_per_ce_emulation_6pe_6vpe_config:

.. option:: -cust_ce_bgp_as_step_per_ce

                 Specifies the step value by which to generate additional AS
                 numbers across CE routers on the customer side. Possible values
                 range from 0 to 65535. The default value is 1. This argument is
                 available when -cust_ce_bgp_as_step_per_ce_enable is set to true. 

.. _cust_ce_bgp_as_step_per_vrf_enable_emulation_6pe_6vpe_config:

.. option:: -cust_ce_bgp_as_step_per_vrf_enable

                 Enables or disables the step value for additional CE AS numbers
                 across VPNs on the customer side. Possible values are true
                 (enable) and false (disable). The default value is true. This
                 argument is available when -cust_ce_routing_protocol is set to
                 BGP or mixed.

.. _cust_ce_bgp_as_step_per_vrf_emulation_6pe_6vpe_config:

.. option:: -cust_ce_bgp_as_step_per_vrf

                 Specifies the step value by which to generate additional CE AS
                 numbers across VPNs on the customer side. Possible values range
                 from 0 to 65535. The default value is 1. This argument is
                 available when -cust_ce_bgp_as_step_per_vrf_enable is set to
                 true.

.. _cust_ce_bgp_4byte_as_enable_emulation_6pe_6vpe_config:

.. option:: -cust_ce_bgp_4byte_as_enable

                 Enables or disables 4-byte AS numbers on the customer side.
                 Possible values are true (enable) and false (disable). The
                 default value is false. This argument is available when
                 -cust_ce_routing_protocol is set to bgp or mixed.

.. _cust_ce_bgp_4byte_as_emulation_6pe_6vpe_config:

.. option:: -cust_ce_bgp_4byte_as

                 Specifies the starting CE 4-byte AS number on the customer side.
                 The default value is 1:01. This argument is available when
                 -cust_ce_bgp_4byte_as_enable is set to true.

.. _cust_ce_bgp_4byte_as_step_per_ce_enable_emulation_6pe_6vpe_config:

.. option:: -cust_ce_bgp_4byte_as_step_per_ce_enable

                 Enables or disables the step value for additional CE 4-byte AS
                 numbers across CE routers on the customer side. Possible values
                 are true (enable) and false (disable). The default value is
                 false. This argument is available when -cust_ce_routing_protocol
                 is set to bgp or mixed and -cust_ce_bgp_4byte_as_enable is set to
                 true.

.. _cust_ce_bgp_4byte_as_step_per_ce_emulation_6pe_6vpe_config:

.. option:: -cust_ce_bgp_4byte_as_step_per_ce

                 Specifies the step value by which to generate additional CE
                 4-byte AS numbers across CE routers on the customer side.
                 Possible values range from 0 to 65535. The default value is 1.
                 This argument is available when
                 -cust_ce_bgp_4byte_as_step_per_ce_enable is set to true.

.. _cust_ce_bgp_4byte_as_step_per_vrf_enable_emulation_6pe_6vpe_config:

.. option:: -cust_ce_bgp_4byte_as_step_per_vrf_enable

                 Enables or disables the step value for additional CE 4-byte AS
                 numbers across VPNs on the customer side. Possible values are
                 true (enable) and false (disable). The default value is true.
                 This argument is available when -cust_ce_routing_protocol is set
                 to bgp or mixed and -cust_ce_bgp_4byte_as_enable is set to true.

.. _cust_ce_bgp_4byte_as_step_per_vrf_emulation_6pe_6vpe_config:

.. option:: -cust_ce_bgp_4byte_as_step_per_vrf

                 Specifies the step value by which to generate additional CE
                 4-byte AS numbers across VPNs on the customer side. Possible
                 values range from 0 to 65535. The default value is 1. This
                 argument is available when
                 -cust_ce_bgp_4byte_as_step_per_vrf_enable is set to true.

.. _cust_rd_start_emulation_6pe_6vpe_config:

.. option:: -cust_rd_start

                 Specifies the starting route distinguisher on the customer side.
                 This argument is available when -vrf_rd_assignment is set to
                 MANUAL. The default value is 1:0.

.. _cust_rd_step_per_vrf_enable_emulation_6pe_6vpe_config:

.. option:: -cust_rd_step_per_vrf_enable

                 Enables or disables the step value for additional customer-side
                 route distinguishers per VPN. Possible values are true and false.
                 The default value is true. 

.. _cust_rd_step_per_vrf_emulation_6pe_6vpe_config:

.. option:: -cust_rd_step_per_vrf

                 Specifies the step value by which to generate additional
                 customer-side route distinguishers per VPN. The default value is
                 1:0.

.. _cust_rd_step_per_ce_enable_emulation_6pe_6vpe_config:

.. option:: -cust_rd_step_per_ce_enable

                 Enables or disables the step value for additional customer-side
                 route distinguishers per CE. Possible values are true and false.
                 The default value is false. 
   
.. _cust_rd_step_per_ce_emulation_6pe_6vpe_config:

.. option:: -cust_rd_step_per_ce

                 Specifies the step value by which to generate additional
                 customer-side route distinguishers per CE. The default value is
                 0:0. This argument is available when -cust_rd_step_per_ce_enable
                 is set to true.
 
.. _cust_route_count_per_ce_emulation_6pe_6vpe_config:

.. option:: -cust_route_count_per_ce

                Specifies the number of routes that will be added to each
                customer-side CE. The default value is 1.
 
.. _provider_pe_vrf_assignment_emulation_6pe_6vpe_config:

.. option:: -provider_pe_vrf_assignment

                 Specifies how VPNs are assigned to PE routers. Possible values
                 are::
                 
                  vpn_per_pe   VPNs will be distributed across a set of PEs
                  pe_per_vpn   PEs will be distributed across a set of VPNs
                  
                 The default value is vpn_per_pe. 

.. _provider_pe_vrf_count_emulation_6pe_6vpe_config:

.. option:: -provider_pe_vrf_count

                 Specifies the number of items (VPNs or PEs) assigned to each
                 target (VPN or PE). When -provider_pe_vrf_assignment is set to
                 vpn_per_pe, this argument indicates the number of VPNs assigned
                 to each PE, and possible values range from 1 to the number of
                 VPNs. When -provider_pe_vrf_assignment is set to pe_per_vpn, this
                 argument indicates the number of PEs assigned to each VPN, and
                 possible values range from 1 to the number of PEs. The default
                 value is 1.
                 
                 If the value is less than the maximum number of items, and there
                 is more than one target, the specified number of items are
                 assigned in a round-robin fashion to each target. This argument
                 is available when -provider_pe_vrf_all_assign is set to false.

.. _provider_pe_vrf_all_assign_emulation_6pe_6vpe_config:

.. option:: -provider_pe_vrf_all_assign

                 Determines whether each PE uses all VPNs. Possible values are
                 true and false. If it is set to false, you can manually set the
                 number of VPNs that each PE will advertise routes for. The
                 default value is false.

.. _provider_ce_bgp_as_enable_emulation_6pe_6vpe_config:

.. option:: -provider_ce_bgp_as_enable

                 Enables or disables BGP AS numbers for CEs on the provider side.
                 Possible values are true (enable) and false (disable). The
                 default value is false.

.. _provider_ce_bgp_as_emulation_6pe_6vpe_config:

.. option:: -provider_ce_bgp_as

                 Specifies the starting BGP AS number on the provider side.
                 Possible values range from 1 to 65535. The default value is 1.
                 This argument is available when -provider_ce_bgp_as_enable is set
                 to true.

.. _provider_ce_bgp_as_step_per_ce_enable_emulation_6pe_6vpe_config:

.. option:: -provider_ce_bgp_as_step_per_ce_enable

                 Enables or disables the step value for additional CE BGP AS
                 numbers across CEs on the provider side. Possible values are true
                 (enable) and false (disable). The default value is false.

.. _provider_ce_bgp_as_step_per_ce_emulation_6pe_6vpe_config:

.. option:: -provider_ce_bgp_as_step_per_ce

                 Specifies the step value by which to generate additional CE BGP
                 AS numbers across CEs on the provider side. Possible values range
                 from 1 to 65535. The default value is 1. This argument is
                 available when -provider_ce_bgp_as_step_per_ce_enable is set to
                 true.

.. _provider_ce_bgp_as_step_per_vrf_enable_emulation_6pe_6vpe_config:

.. option:: -provider_ce_bgp_as_step_per_vrf_enable

                 Enables or disables the step value for additional CE BGP AS
                 numbers across VPNs on the provider side. Possible values are
                 true (enable) and false (disable). The default is true.

.. _provider_ce_bgp_as_step_per_vrf_emulation_6pe_6vpe_config:

.. option:: -provider_ce_bgp_as_step_per_vrf

                 Specifies the step value by which to generate additional CE BGP
                 AS numbers across VPNs on the provider side. Possible values
                 range from 1 to 65535. The default value is 1.
.
.. _provider_ce_bgp_4byte_as_enable_emulation_6pe_6vpe_config:

.. option:: -provider_ce_bgp_4byte_as_enable

                 Enables or disables 4-byte AS numbers for CE routers on the
                 provider side. Possible values are true (enable) and false
                 (disable). The default value is false.

.. _provider_ce_bgp_4byte_as_emulation_6pe_6vpe_config:

.. option:: -provider_ce_bgp_4byte_as

                 Defines the first 4-byte AS number for CEs on the provider side.
                 The default value is 1:01. This argument is available when
                 -provider_ce_bgp_4byte_as_enable is set to true.

.. _provider_ce_bgp_4byte_as_step_per_ce_enable_emulation_6pe_6vpe_config:

.. option:: -provider_ce_bgp_4byte_as_step_per_ce_enable

                 Enables or disables the step value for additional CE 4-byte AS
                 numbers across CEs on the provider side. Possible values are true
                 (enable) and false (disable). The default value is false.
 
.. _provider_ce_bgp_4byte_as_step_per_ce_emulation_6pe_6vpe_config:

.. option:: -provider_ce_bgp_4byte_as_step_per_ce

                 Specifies the step value by which to generate additional CE
                 4-byte AS numbers across CEs on the provider side. Possible
                 values range from 1 to 65535. The default value is 1. This
                 argument is available when
                 -provider_ce_bgp_4byte_as_step_per_ce_enable is set to true.

.. _provider_ce_bgp_4byte_as_step_per_ce_emulation_6pe_6vpe_config:

.. option:: -provider_ce_bgp_4byte_as_step_per_ce

                 Specifies the step value for additional CE 4-byte AS numbers
                 across CE routers on the provider side. Possible values range
                 from 0 to 65535. The default value is 1. This argument is
                 available when -provider_ce_bgp_4byte_as_step_per_ce_enable is
                 set to true.

.. _provider_ce_bgp_4byte_as_step_per_vrf_enable_emulation_6pe_6vpe_config:

.. option:: -provider_ce_bgp_4byte_as_step_per_vrf_enable

                 Enables or disables the step value for additional CE 4-byte AS
                 numbers per VPN on the provider side. Possible values are true
                 (enable) and false (disable). The default value is true.

.. _provider_ce_bgp_4byte_as_step_per_vrf_emulation_6pe_6vpe_config:

.. option:: -provider_ce_bgp_4byte_as_step_per_vrf

                 Specifies the step value by which to generate additional CE
                 4-byte AS numbers across VPNs on the provider side. Possible
                 values range from 1 to 65535. The default value is 1.
 
.. _provider_rd_start_emulation_6pe_6vpe_config:

.. option:: -provider_rd_start

                 Specifies the starting route distinguisher for provider sites.
                 The default value is 1:0.
 
.. _provider_rd_step_per_vrf_enable_emulation_6pe_6vpe_config:

.. option:: -provider_rd_step_per_vrf_enable

                 Enables or disables the step value for additional route
                 distinguishers per VPN on the provider side. Possible values are
                 true (enable) and false (disable). The default value is true. 
               

.. _provider_rd_step_per_vrf_emulation_6pe_6vpe_config:

.. option:: -provider_rd_step_per_vrf

                 Specifies the step value by which to generate additional route
                 distinguishers across VPNs on the provider side. The default
                 value is 1:0.

.. _provider_rd_step_per_ce_enable_emulation_6pe_6vpe_config:

.. option:: -provider_rd_step_per_ce_enable

                 Enables or disables the step value for additional route
                 distinguishers across CE routers on the provider side. Possible
                 values are true (enable) and false (disable). The default value
                 is false.
         
.. _provider_rd_step_per_ce_emulation_6pe_6vpe_config:

.. option:: -provider_rd_step_per_ce

                 Specifies the step value by which to generate additional route
                 distinguishers across CE routers on the provider side. The
                 default value is 0:0.
 
.. _cust_ipv6_vpn_route_start_emulation_6pe_6vpe_config:

.. option:: -cust_ipv6_vpn_route_start

                 Specifies the first IPv6 route advertised by emulated CE routers.
                 The value must be in IPv6 format. The default value is 2001::.
 
.. _cust_ipv6_vpn_route_step_emulation_6pe_6vpe_config:

.. option:: -cust_ipv6_vpn_route_step

                 Identifies which part of the IPv6 address to increment for
                 subsequent routes on the customer side. The default value is 1.

.. _cust_ipv6_vpn_route_prefix_len_emulation_6pe_6vpe_config:

.. option:: -cust_ipv6_vpn_route_prefix_len

                 Identifies the IPv6 network portion of the starting route
                 identifier on the customer side. Possible values range from 1 to
                 128. The default value is 64.
 
.. _cust_ipv6_vpn_route_overlap_emulation_6pe_6vpe_config:

.. option:: -cust_ipv6_vpn_route_overlap

                 Determines how routes are advertised on the customer side.
                 Possible values are true and false. When set to true, all VPNs
                 advertise the same routes. When set to false, each VPN advertises
                 unique routes. The default value is false.

.. _cust_ipv6_ce_route_type_emulation_6pe_6vpe_config:

.. option:: -cust_ipv6_ce_route_type

                 Specifies the type of IPv6 routes to be advertised by
                 emulated CEs on the customer side. Possible values are::
                 
                  internal      The route and the CE that advertise the route 
                                are in the same AS
                                
                  external      The route and the CE that advertise the route 
                                    are not in the same AS
                                    
                 The default value is internal.  This argument is
                 available when -cust_ce_routing_protocol is set to OSPF or
                 ISIS.
             
.. _provider_ipv6_vpn_route_start_emulation_6pe_6vpe_config:

.. option:: -provider_ipv6_vpn_route_start

                 Specifies the first IPv6 route advertised by emulated PE routers
                 on the provider side. The value must be in IPv6 format. The
                 default value is 2001::.
 
.. _provider_ipv6_vpn_route_step_emulation_6pe_6vpe_config:

.. option:: -provider_ipv6_vpn_route_step

                 Identifies which part of the IPv6 address to increment for
                 subsequent routes on the provider side. The default value is 1.
 
.. _provider_ipv6_vpn_route_prefix_len_emulation_6pe_6vpe_config:

.. option:: -provider_ipv6_vpn_route_prefix_len

                 Identifies the IPv6 network portion of the starting route
                 identifier on the provider side. Possible values range from 1 to
                 128. The default value is 64.
 
.. _provider_ipv6_vpn_route_overlap_emulation_6pe_6vpe_config:

.. option:: -provider_ipv6_vpn_route_overlap

                 Determines how routes are advertised on the provider side.
                 Possible values are true and false. When set to true, all VPNs
                 advertise the same routes. When set to false, each VPN advertises
                 unique routes. The default value is false.
 
.. _provider_route_count_per_ce_emulation_6pe_6vpe_config:

.. option:: -provider_route_count_per_ce

                 Specifies the number of routes that will be added to each CE
                 router on the provider side. The default value is 1.

.. _vrf_route_mpls_label_type_emulation_6pe_6vpe_config:

.. option:: -vrf_route_mpls_label_type

                 Defines the method by which labels are assigned within a traffic
                 block.  Possible values are::
                 
                  label_per_site     All routes in one traffic route are
                                     advertised with the same label
                                    
                  label_per_route    Each route in one traffic route is
                                     advertised with a unique label
     
                 The default value is label_per_site.
                 
.. _vrf_route_mpls_label_start_emulation_6pe_6vpe_config:

.. option:: -vrf_route_mpls_label_start

                 Specifies the first MPLS label to be assigned to VPN routes on
                 the provider side. Possible values range from 1 to 1048575. The
                 default value is 16.

.. _traffic_flow_direction_emulation_6pe_6vpe_config:

.. option:: -traffic_flow_direction

                 Specifies the type of traffic flows to create. This argument is
                 available when -traffic_enable is set to true. Possible
                 values are described below::
                 
                   cust_to_core   Traffic is created from the customer side to
                                  the core side
                   
                   core_to_cust   Traffic is created from the core side to
                                  the customer side
                   
                   bidirectional  Traffic is created from  both directions
                   
                   fully_meshed   Traffic is created in a fully meshed pattern  
                   
                   none           None
                  
                  The default value is bidirectional.

.. _traffic_pattern_emulation_6pe_6vpe_config:

.. option:: -traffic_pattern

                 Specifies the traffic mapping method to be used within each host
                 block. Possible values are::
                 
                  one_to_one    Every endpoint within the source endpoint block 
                                transmits traffic to the corresponding endpoint
                                within the destination endpoint block
                                
                  one_to_many   Every endpoint within the source endpoint block
                                transmits traffic to all endpoints within the
                                destination endpoint block

.. _traffic_stream_group_method_emulation_6pe_6vpe_config:

.. option:: -traffic_stream_group_method

                 Determines how to aggregate streams in a streamblock.
                 Possible values are::
                 
                  aggregate  Aggregates all streams into a single streamblock
                  
                  vpn        Aggregates all streams for a single VPN into a
                             single stream block
 
.. _traffic_use_single_stream_per_endpoint_pair_emulation_6pe_6vpe_config:

.. option:: -traffic_use_single_stream_per_endpoint_pair

                 Determines whether Spirent HLTAPI will assign a single stream ID
                 to each endpoint pair. Possible values are true and false. The
                 default value is false. 

.. _traffic_load_percent_provider_emulation_6pe_6vpe_config:

.. option:: -traffic_load_percent_provider

                 Specifies the load percentage for test traffic from each
                 provider-side port. Possible values range from 0 to 100. The
                 default value is 10.

.. _traffic_load_percent_cust_emulation_6pe_6vpe_config:

.. option:: -traffic_load_percent_cust

                 Specifies the load percentage for test traffic from each
                 customer-side port. Possible values range from 0 to 100. The
                 default value is 10.

Return Values
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Depending on the specific language that HLTAPI uses, the function returns a
keyed list/dictionary/hash (See Introduction for more information on return
value formats) using the following keys (with corresponding data)::

 handle      6PE/6VPE network configuration handle created by this function
 status      Success or Failure of the operation
 log         Error message if command returns {status 0}

The following keys are returned when you specify -mode create::
  
  ce_router           CE router handle
  p_router            P router handle
  rr_router           RR router handle
  pe_router           PE router handle
  vpn                 VPN handle 
  ospf                OSPF SR handle
  isis                ISIS SR handle
  ldp                 LDP handle
  rsvp                RSVP-TE handle 
  bgp                 BGP handle
  bfd                 BFD handle
  rip                 RIP handle
  stream_id           Streamblock handle


Description
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The ``sth::emulation_6pe_6vpe_config`` function creates or deletes 6PE/6VPE network
topologies, mapping the operations of the 6PE or 6VPE Wizard in the Spirent
TestCenter GUI. Use the -mode argument to specify the action to perform.
   
Before you use the function, you must configure customer and provider test ports
using the sth::emulation_6pe_6vpe_cust_port_config and
``sth::emulation_6pe_6vpe_provider_port_config`` functions.
   
If the operation fails, Spirent HLTAPI returns an error message.
  
Examples
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following example creates a 6VPE network topology::

 sth::emulation_6pe_6vpe_config 
      -mode create 
      -dut_router_id  10.0.0.1 
      -dut_as  2 
      -dut_4byte_as_enable  true 
      -cust_use_ports_enable  true 
      -provider_use_ports_enable  true 
      -igp_protocol  ospf  
      -mpls_protocol  ospf 
      -igp_ospf_area_id 0.0.0.0 
      -igp_ospf_network_type native 
      -igp_ospf_router_priority 0
      -igp_ospf_interface_cost 1 
      -igp_ospf_options  0x42
      -igp_ospf_auth_mode md5 
      -igp_ospf_auth_password  abc 
      -igp_ospf_auth_md5_key  1 
      -igp_ospf_bfd_enable   true 
      -p_router_enable true 
      -vpn_6vpe_enable  true 
      -bgp_route_reflector_enable true 
      -bgp_bfd_enable true 
      -cust_ce_bgp_as_step_per_ce_enable true 
      -cust_ce_bgp_as_step_per_vrf_enable true 
      -cust_ce_bgp_4byte_as_enable true 
      -cust_ce_bgp_4byte_as_step_per_ce_enable true 
      -cust_ce_bgp_4byte_as_step_per_vrf_enable true 
      -cust_rd_step_per_vrf_enable true 
      -cust_rd_step_per_ce_enable true 
      -provider_pe_vrf_all_assign true 
      -provider_ce_bgp_as_enable true 
      -provider_ce_bgp_as_step_per_ce_enable  true 
      -provider_ce_bgp_as_step_per_vrf_enable true 
      -provider_ce_bgp_4byte_as_enable true 
      -provider_ce_bgp_4byte_as_step_per_ce_enable true 
      -provider_ce_bgp_4byte_as_step_per_vrf_enable true 
      -provider_rd_step_per_vrf_enable  true 
      -provider_rd_step_per_vrf  1:1 
      -provider_rd_step_per_ce_enable  true 
      -cust_ipv6_vpn_route_overlap  true 
      -provider_ipv6_vpn_route_overlap   true 
      -traffic_use_single_stream_per_endpoint_pair true 

Sample output::

 {status 1} {handle {{vpn {vpnidgroup1 vpnidgroup2 vpnidgroup3 vpnidgroup4
 vpnidgroup5 vpnidgroup6 vpnidgroup7 vpnidgroup8 vpnidgroup9 vpnidgroup10}}
 {ce_router {router21 router22 router23 router24 router25 router26 router27
 router28 router29 router30}} {p_router {router1 router3 router5 router7 router9
 router11 router13 router15 router17 router19}} {rr_router {router2 router4
 router6 router8 router10 router12 router14 router16 router18 router20}}
 {pe_router {}} {ospf {ospfv2routerconfig1 ospfv2routerconfig2 ospfv2routerconfig3
 ospfv2routerconfig4 ospfv2routerconfig5 ospfv2routerconfig6 ospfv2routerconfig7
 ospfv2routerconfig8 ospfv2routerconfig9 ospfv2routerconfig10}} {isis {}} {ldp {}}
 {rsvp {}} {bgp {bgprouterconfig1 bgprouterconfig2 bgprouterconfig3
 bgprouterconfig4 bgprouterconfig5 bgprouterconfig6 bgprouterconfig7
 bgprouterconfig8 bgprouterconfig9 bgprouterconfig10 bgprouterconfig11
 bgprouterconfig12 bgprouterconfig13 bgprouterconfig14 bgprouterconfig15
 bgprouterconfig16 bgprouterconfig17 bgprouterconfig18 bgprouterconfig19
 bgprouterconfig20}} {bfd {bfdrouterconfig1 bfdrouterconfig2 bfdrouterconfig3
 bfdrouterconfig4 bfdrouterconfig5 bfdrouterconfig6 bfdrouterconfig7
 bfdrouterconfig8 bfdrouterconfig9 bfdrouterconfig10 bfdrouterconfig11
 bfdrouterconfig12 bfdrouterconfig13 bfdrouterconfig14 bfdrouterconfig15
 bfdrouterconfig16 bfdrouterconfig17 bfdrouterconfig18 bfdrouterconfig19
 bfdrouterconfig20}} {rip {}} {stream_id {streamblock1 streamblock2}}}}



sth::emulation_6pe_6vpe_control 
---------------------------------------------------
 
Purpose
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

:orange:`Spirent Extension (for Spirent HLTAPI only).`

 
Starts or stops the specified 6PE/6VPE topology

Synopsis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. parsed-literal::


 sth::emulation_6pe_6vpe_control 
     -port_handle <port_handle> | -handle <handle>
     -action {start|stop} 

Arguments:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. _port_handle_emulation_6pe_6vpe_control:

.. option:: -port_handle

                 Specifies the port on which routers will start or stop. You must
                 specify either -handle or -port_handle, but not both.
 
.. _handle_emulation_6pe_6vpe_control:

.. option:: -handle

                 Specifies the routers to start or stop. You must specify either
                 -handle or -port_handle, but not both.
 
.. _action_emulation_6pe_6vpe_control:

.. option:: -action

                 Specifies the action to performed. This argument is mandatory.
                 Possible values are described below::
                     
                  start   Starts the specified 6PE/6VPE network
                  
                  stop    Stops the specified 6PE/6VPE network
 
Return Values
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Depending on the specific language that HLTAPI uses, the function returns a
 keyed list/dictionary/hash (See Introduction for more information on return
 value formats) using the following keys (with corresponding data)::
     
     status          Success (1) or failure (0) of the operation
             
     log             An error message (if the operation failed)

Description
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 The ``sth::emulation_6pe_6vpe_control`` function controls the configured 6PE/6VPE
 topology. Use the -action argument to start or stop the test.

Examples
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Sample Input::
   
 sth::emulation_6pe_6vpe_control 
     -port_handle $port1 port2 
     -action start

Sample Output::
     
     {status 1}


sth::emulation_6pe_6vpe_info
---------------------------------------------------

Purpose
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

:orange:`Spirent Extension (for Spirent HLTAPI only).`


Retrieves statistics for the 6PE/6VPE test

Synopsis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. parsed-literal::


 sth::emulation_6pe_6vpe_info 
     -handle <handle> | -port_handle <port_handle>
     -mode {rsvp|ldp|isis|ospfv2|ospfv3|bgp|rip|bfd|summary}

Arguments
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. _handle_emulation_6pe_6vpe_info:

.. option:: -handle

                 Specifies the router from which to retrieve statistics. You 
                 must specify either -handle or -port_handle, but not both.
 
.. _port_handle_emulation_6pe_6vpe_info:

.. option:: -port_handle

                 Specifies the port from which to retrieve statistics
                 
.. _mode_emulation_6pe_6vpe_info:

.. option:: -mode

                 Determines the protocol for which statistics will be retrieved.
                 This argument is mandatory. Possible values are rsvp, ldp, isis,
                 ospfv2, bgp, rip, bfd, and summary.

Return Values
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Depending on the specific language that HLTAPI uses, the function returns a keyed
list/dictionary/hash (See Introduction for more information on return value
formats) using the following keys (with corresponding data)::
     
   status            Success (1) or failure (0) of the operation
           
   log                An error message (if the operation failed)

The following keys are returned when you specify -mode rsvp::
 
 EventInProgress                 Event in progress
 TxPath                          Number of PATH messages sent
 RxPath                          Number of PATH messages received
 TxReservation                   Number of Reservation messages sent
 RxReservation                   Number of Reservation messages received
 TxPathError                     Number of PATH Error messages sent
 RxPathError                     Number of PATH Error messages received
 TxReservationError              Number of Reservation Error messages sent
 RxReservationError              Number of Reservation Error messages received
 TxReservationConfirmation       Number of Reservation Confirm messages sent
 RxReservationConfirmation       Number of Reservation Confirm messages received
 TxPathTeardown                  Number of PATH Tear Down messages sent
 RxPathTeardown                  Number of PATH Tear Down messages received
 TxReservationTeardown           Number of Reservation Tear Down messages sent
 RxReservationTeardown           Number of Reservation Tear Down messages received
 LspUpCount                      Number of LSPs in Up state
 LspDownCount                    Number of LSPs in Down state
 LspConnectingCount              Number of LSPs in Connecting state
 MinLspSetupTime                 Minimum time (in ms) to set up an LSP on the session
 MaxLspSetupTime                 Maximum time (in ms) to set up an LSP on the session
 AvgLspSetupTime                 Average time (in ms) to set up an LSP on the session
 LastTxReservationErrorCode      Reports the last Reservation Error message code sent
 LastRxReservationErrorCode      Reports the last Reservation Error message code received
 LastTxPathErrorCode             Reports the last PATH Error message code sent
 LastRxPathErrorCode             Reports the last PATH Error message code received
 TxHello                         Number of Hello packets sent
 RxHello                         Number of Hello packets received
 TxPathRecovery                  Number of PATH Recovery packets sent
 RxPathRecovery                  Number of PATH Recovery packets received
 EgressLspUpCount                Number of egress LSPs in Up state
 TxNotify                        Number of Notify packets sent
 RxNotify                        Number of Notify packets received
 Timestamp                       Timestamp of the results

 The following keys are returned when you specify -mode ldp::
 
 TxDirectHellosCount             Number of direct Hellos sent
 TxIpv4DirectHellosCount         Number of IPv4 direct Hellos sent
 TxIpv6DirectHellosCount         Number of IPv6 direct Hellos sent
 RxDirectHellosCount             Number of direct Hellos received
 RxIpv4DirectHellosCount         Number of IPv4 direct Hellos received
 RxIpv6DirectHellosCount         Number of IPV6 direct Hellos received
 TxTargetedHellosCount           Number of targeted Hellos sent
 TxIpv4TargetedHellosCount       Number of IPv4 targeted Hellos sent
 TxIpv6TargetedHellosCount       Number of IPv6 targeted Hellos sent
 RxTargetedHellosCount           Number of targeted Hellos received
 RxIpv4TargetedHellosCount       Number of IPv4 targeted Hellos received
 RxIpv6TargetedHellosCount       Number of IPv6 targeted Hellos received
 LspUpCount                      Number of LSPs in Up state
 NumLspDownCount                 Number of LSPs in Down state
 TxKeepAliveCount                Number of Keepalives sent
 RxKeepAliveCount                Number of Keepalives received
 TxLabelRequestsCount            Number of Label Requests sent
 RxLabelRequestsCount            Number of Label Requests received
 TxLabelMappingCount             Number of Label Mapping messages sent
 RxLabelMappingCount             Number of Label Mapping messages received
 TxLabelAbortCount               Number of Label Abort requests sent
 RxLabelAbortCount               Number of Label Abort requests received
 TxLabelWithdrawCount            Number of Label Withdraw messages sent
 RxLabelWithdrawCount            Number of Label Withdraw messages received
 TxLabelReleaseCount             Number of Label Release messages sent
 RxLabelReleaseCount             Number of Label Release messages received
 TxNotificationCount             Number of Notification messages sent
 RxNotificationCount             Number of Notification messages received
 TxAddrWithdrawCount             Number of Address Withdraw messages sent
 RxAddrWithdrawCount             Number of Address Withdraw messages received
 TxNotifyCode                    Notification code sent in string format  
 RxNotifyCode                    Notification code received in string format  
 LdpSessionVersion               LDP session version

The following keys are returned when you specify -mode isis::
 
 TxPtpHelloCount                 Number of point-to-point Hellos sent to the SUT
 RxPtpHelloCount                 Number of point-to-point Hellos received from the SUT
 TxL1LanHelloCount               Number of L1 Tx LAN Hellos sent to the SUT
 RxL1LanHelloCount               Number of L1 Rx LAN Hellos received from the SUT
 TxL1LspCount                    Number of L1 Tx LSPs sent to the SUT
 RxL1LspCount                    Number of L1 Rx LSPs received from the SUT
 TxL1CsnpCount                   Number of L1 Tx CSNPs sent to the SUT
 RxL1CsnpCount                   Number of L1 Rx CSNPs received from the SUT
 TxL1PsnpCount                   Number of L1 Tx PSNPs sent to the SUT
 RxL1PsnpCount                   Number of L1 Rx PSNPs received from the SUT
 TxL2LanHelloCount               Number of L2 Tx LAN Hellos sent to the SUT
 RxL2LanHelloCount               Number of L2 Rx LAN Hellos received from the SUT
 TxL2LspCount                    Number of L2 Tx LSPs sent to the SUT
 RxL2LspCount                    Number of L2 Rx LSPs received from the SUT
 TxL2CsnpCount                   Number of L2 Tx CSNPs sent to the SUT
 RxL2CsnpCount                   Number of L2 Rx CSNPs received from the SUT
 TxL2PsnpCount                   Number of L2 Tx PSNPs sent to the SUT
 RxL2PsnpCount                   Number of L2 Rx PSNPs received from the SUT
 AdjacencyLevel                  Adjacency level

The following keys are returned when you specify -mode ospfv2::
 
 TxHello                         Number of Hello packets sent by the emulated router
 RxHello                         Number of Hello packets received by the emulated router
 TxDd                            Number of Database Description packets sent by the emulated router
 RxDd                            Number of Database Description packets received by the emulated router
 TxRouterLsa                     Number of Router LSAs sent by the emulated router
 RxRouterLsa                     Number of Router LSAs received by the emulated router
 TxNetworkLsa                    Number of Network LSAs sent by the emulated router
 RxNetworkLsa                    Number of Network LSAs received by the emulated router
 TxSummaryLsa                    Number of Summary LSAs sent by the emulated router
 RxSummaryLsa                    Number of Summary LSAs received by the emulated router
 TxAsbrSummaryLsa                Number of ASBR-Summary LSAs sent by the emulated router
 RxAsbrSummaryLsa                Number of ASBR-Summary-LSAs received by the emulated router
 TxAsExternalLsa                 Number of External LSAs sent by the emulated router
 RxAsExternalLsa                 Number of External LSAs received by the emulated router
 TxNssaLsa                       Number of NSSA LSAs sent by the emulated router
 RxNssaLsa                       Number of NSSA LSAs received by the emulated router
 TxAck                           Number of LSA packets sent by the emulated router
 RxAck                           Number of LSA packets received by the emulated router
 TxRequest                       Number of LS Request packets sent by the emulated router
 RxRequest                       Number of LS Request packets received by the emulated router
 TxUpdate                        Number of Update messages sent
 RxUpdate                        Number of Update messages received
 TxTeLsa                         Number of TE-LSAs sent by the emulated router
 RxTeLsa                         Number of TE-LSAs received by the emulated router
 TxRiLsa                         Number of Router Info LSAs sent by the emulated router
 RxRiLsa                         Number of Router Info LSAs received by the emulated router
 TxEpLsa                         Number of Extended Prefix LSAs sent by the emulated router
 RxEpLsa                         Number of Extended Prefix LSAs received by the emulated router
 TxElLsa                         Number of Extended Link LSAs sent by the emulated router
 RxElLsa                         Number of Extended Link LSAs received by the emulated router
 SessionUpCount                  Session up count
 areaId                          Area ID
 ipv4SrcAddr                     IPv4 source address


The following keys are returned when you specify -mode ospfv3::
   
 TxHello                         Number of Hello packets sent
 RxHello                         Number of Hello packets received
 TxDd                            Number of Database Description packets sent
 RxDd                            Number of Database Description packets received
 TxRouterLsa                     Number of Router LSAs sent
 RxRouterLsa                     Number of Router LSAs received
 TxNetworkLsa                    Number of Network LSAs sent
 RxNetworkLsa                    Number of Network LSAs received
 TxSummaryLsa                    Number of Summary LSAs sent
 RxSummaryLsa                    Number of Summary LSAs received
 TxAsbrSummaryLsa                Number of ASBR-Summary LSAs sent
 RxAsbrSummaryLsa                Number of ASBR-Summary-LSAs received
 TxAsExternalLsa                 Number of External LSAs sent
 RxAsExternalLsa                 Number of External LSAs received
 TxNssaLsa                       Number of NSSA LSAs sent
 RxNssaLsa                       Number of NSSA LSAs received
 TxAck                           Number of LSA packets sent
 RxAck                           Number of LSA packets received
 TxRequest                       Number of LS Request packets sent
 RxRequest                       Number of LS Request packets received
 TxUpdate                        Number of Update messages sent
 RxUpdate                        Number of Update messages received
 RxIntraAreaPrefixLsa            Number of Intra-Area-Prefix LSAs received
 TxIntraAreaPrefixLsa            Number of Intra-Area-Prefix LSAs sent 
 RxInterAreaPrefixLsa            Number of inter-area-prefix LSAs received  
 TxInterAreaPrefixLsa            Number of inter-area-prefix LSAs sent  
 RxInterAreaRouterLsa            Number of inter-area-router LSAs received 
 TxInterAreaRouterLsa            Number of inter-area-router LSAs sent 
 RxLinkLsa                       Number of link LSAs received 
 TxLinkLsa                       Number of link LSAs sent 
 TxNssaLsa                       Number of NSSA LSAs sent  
 RxNssaLsa                       Number of Link LSAs received
 RxERouterLsa                    Number of Extended Router LSAs received
 TxERouterLsa                    Number of Extended Router LSAs sent
 RxENetworkLsa                   Number of Extended Network LSAs received
 TxENetworkLsa                   Number of Extended Network LSAs sent
 RxEIntraAreaPrefixLsa           Number of Extended Intra-Area Prefix LSAs received
 TxEIntraAreaPrefixLsa           Number of Extended Intra-Area Prefix LSAs sent
 RxEInterAreaPrefixLsa           Number of Extended Inter-Area Prefix LSAs received
 TxEInterAreaPrefixLsa           Number of Extended Inter-Area Prefix LSAs sent
 RxEInterAreaRouterLsa           Number of Extended Inter-Area Router LSAs received
 TxEInterAreaRouterLsa           Number of Extended Inter-Area Router LSAs sent
 RxELinkLsa                      Number of Extended Link LSAs received
 TxELinkLsa                      Number of Extended Link LSAs sent

The following keys are returned when you specify -mode bgp::
 
 TxAdvertisedRouteCount      Total cumulative feasible routes the emulated router
                             has sent out in all UPDATE packets
 RxAdvertisedRouteCount      Total cumulative feasible routes received by 
                             the emulated router
 TxWithdrawnRouteCount       Total number of unfeasible routes the emulated router
                             has sent out in all UPDATE packets
 RxWithdrawnRouteCount       Total cumulative unfeasible routes received 
                             by the emulated router
 TxNotificationCount         Number of Notification packets sent from the 
                             emulated router
 RxNotificationCount         Number of Notification packets received by
                             the emulated router 
 TxAdvertisedUpdateCount     Total number of UPDATE packets with feasible routes
                             sent to the DUT
 RxAdvertisedUpdateCount     Number of Update packets received from DUT
 TxWithdrawnUpdateCount      Total number of UPDATE packets with unfeasible
                             routes sent to the DUT (route flapping)
 TxKeepAliveCount            Total number of KEEPALIVE packets sent to the DUT
 RxKeepAliveCount            Total number of KEEPALIVE packets received from
                             the DUT during the test
 TxOpenCount                 Total number of OPEN packets sent to the DUT
 RxOpenCount                 BGP Open messages received from DUT  
 TxRouteRefreshCount         Number of advertised Route Refresh messages transmitted
 RxRouteRefreshCount         Number of advertised Route Refresh messages received
 OutstandingRouteCount       Number of routes that should be in the DUT's current route table
 LastRxUpdateRouteCount      Number of routes in the last-received UPDATE message
 TxNotifyCode                Last Notification code the emulated router sent to the DUT
 TxNotifySubCode             Sub-code for the last Notification sent to the DUT
 RxNotifyCode                Last Notification code the emulated router received from the DUT
 RxNotifySubCode             Sub-code for the last Notification received from the DUT
 TxRtConstraintCount         Number of RT-Constraint routes sent for this router
 RxRtConstraintCount         Number of RT-Constraint routes received for this router
 SessionUpCount              Number of router sessions within the router block in
                             Established state

The following keys are returned when you specify -mode rip::
 
 TxAdvertisedUpdateCount     Number of advertised routes sent by the emulated router
 RxAdvertisedUpdateCount     Number of advertised routes received by the emulated router
 TxWithdrawnUpdateCount      Number of unreachable (metric 16) routes sent by the emulated router
 RxWithdrawnUpdateCount      Number of unreachable (metric 16) routes received by the emulated router

The following keys are returned when you specify -mode bfd::
 
 TimeoutCount                Number of timeout conditions detected by BFD
 FlapCount                   Number of times a flap event was detected by BFD
 TxCount                     Number of BFD packets sent on this router
 RxCount                     Number of BFD packets received on this router

The following keys are returned when you specify -mode summary::
 
 ldp_summaryportxSessionDownCount          Number of routers in SessionDown state
 ldp_summaryportxSessionUpCount            Number of routers in SessionUp state
 ldp_summaryportxSessionFailedCount        Number of routers in SessionFailed state
 ldp_summaryportxSessionOpenCount          Number of routers in SessionOpen state
 ldp_summaryportxSessionConnectCount       Number of routers in SessionConnect state
 ldp_summaryportxSessionRestartCount       Number of routers in SessionRestart state
 ldp_summaryportxSessionHelperCount        Number of routers in SessionHelper state
 
 bgp_summaryportxIdleCount                 Number of routers in Idle state
 bgp_summaryportxConnectCount              Number of routers in Connect state
 bgp_summaryportxActiveCount               Number of routers in Active state
 bgp_summaryportxOpenSentCount             Number of routers in Open Sent state
 bgp_summaryportxOpenConfirmCount          Number of routers in Open Confirm state
 bgp_summaryportxEstablishedCount          Number of routers in Established state
   
 bfd_summaryportxSessionsUpCount           Number of BFD sessions in Up state
 bfd_summaryportxSessionsDownCount         Number of BFD sessions in Down and AdminDown state
 bfd_summaryportxMicroBfdSessionsUpCount   Number of Micro-BFD sessions in Up state
 bfd_summaryportxMicroBfdSessionsDownCount Number of Micro-BFD sessions in Down and AdminDown state
 
 
 ospf_summaryportxDownCount             Number of OSPFv2 routers in Down state
 ospf_summaryportxWaitingCount          Number of OSPFv2 routers in Waiting state
 ospf_summaryportxP2PCount              Number of OSPFv2 routers in P2P state
 ospf_summaryportxDrOtherCount          Number of OSPFv2 routers in DrOther state
 ospf_summaryportxBackupCount           Number of OSPFv2 routers in Backup state
 ospf_summaryportxDrCount               Number of OSPFv2 routers in Dr state
 
     
 ospfv3_SummaryPortxDownCount         Number of OSPFv3 routers in Down state
 ospfv3_SummaryPortxWaitingCount      Number of OSPFv3 routers in Waiting state
 ospfv3_SummaryPortxP2PCount          Number of OSPFv3 routers in P2P state
 ospfv3_SummaryPortxDrOtherCount      Number of OSPFv3 routers in Dr Other state
 ospfv3_SummaryPortxBackupCount       Number of OSPFv3 routers in Backup state
 ospfv3_SummaryPortxDrCount           Number of OSPFv3 routers in Dr state
 
 isis_summaryportxIdleCount             Number of routers in Idle state
 isis_summaryportxInitCount             Number of routers in INIT state
 isis_summaryportxUpCount               Number of routers in Up state
 isis_summaryportxGrCount               Number of routers in GR state
 isis_summaryportxGrHelperCount         Number of routers in GR Helper state
 
 rsvp_summaryportx 
 rsvp_summaryportxDownCount             Number of routers in Down state
 rsvp_summaryportxInitCount             Number of routers in INIT state
 rsvp_summaryportxUpCount               Number of routers in Up state
 
 rip_summaryportxRouterUpCount          Number of routers in Open state
 rip_summaryportxRouterDownCount        Number of routers in NotStarted/Closed state

Description
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The ``sth::emulation_mvpn_info`` function provides information about
the configured 6PE/6VPE network topology.
  
Examples
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following example retrieves OSPFv2 statistics from a specified router::
 
   sth::emulation_6pe_6vpe_info 
      -handle $routerList 
      -mode ospfv2]

Sample output::
 
 {ospf_results {{port1 {{router1 {{TxHello 2} {RxHello 0} {TxDd 0} {RxDd 0}
 {TxRouterLsa 0} {RxRouterLsa 0} {TxNetworkLsa 0} {RxNetworkLsa 0} {TxSummaryLsa
 0} {RxSummaryLsa 0} {TxAsbrSummaryLsa 0} {RxAsbrSummaryLsa 0} {TxAsExternalLsa 0}
 {RxAsExternalLsa 0} {TxNssaLsa 0} {RxNssaLsa 0} {TxAck 0} {RxAck 0} {TxRequest 0}
 {RxRequest 0} {TxUpdate 0} {RxUpdate 0} {TxTeLsa 0} {RxTeLsa 0} {TxRiLsa 0}
 {RxRiLsa 0} {TxEpLsa 0} {RxEpLsa 0} {TxElLsa 0} {RxElLsa 0} {SessionUpCount 0}
 {areaId 0.0.0.0} {ipv4SrcAddr 192.85.1.2}}}}}}} {status 1}
