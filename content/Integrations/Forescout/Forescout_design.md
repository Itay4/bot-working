## Integration Design

### forescout-get-hosts
Retrieve a list of active endpoints. The command returns a list of all active endpoints in the Forescout platform unless the optional inputs are used to filter the results. Results can be filtered by host property values of the endpoint and policies that select the endpoint.
**endpoint**: `https://{EM.IP}/api/hosts`
**inputs**:

- *rule_ids* -> List of internal identifier strings of active policies defined in the Forescout platform. Only endpoints that are selected by ALL of the entered policies or rules are returned. _Optional_  
- *properties* -> List of property, value assignments by which to filter hosts. _Optional_

**outputs**:
- *Host ID*
- *Host IP*
- *Host MAC Address*
- *Host Endpoint URL*


### forescout-get-host
Retrieve specified host property values for an endpoint.
**endpoint**: `https://{EM.IP}/api/hosts/ip/{ipv4}`, `https://{EM.IP}/api/hosts/mac/{mac}`, `https://{EM.IP}/api/hosts/{obj_ID}`
**inputs**:

- *identifier* -> To retrieve an endpoint by its IP address enter 'ip={ip-address}' where {ip-address} is replaced by the desired IP address. Similarly to search by MAC address or object ID enter 'mac={mac-address}' and 'id={object-id}' respectively where the contents between the curly braces is replaced by the actual identifier. _Required_  
- *fields* -> List of host properties to include in the output for the targeted endpoint. _Optional_

**outputs**:

- *Host ID*
- *Host IP*
- *Host MAC Address*
- *Host Endpoint URL*
- *Host Fields*


### forescout-get-hostfields
Retrieve an index of Forescout host properties.
**endpoint**: `https://{EM.IP}/api/hostfields`
**inputs**:

**outputs**:

- *All potential Host properties*


### forescout-update-host-properties
Set property values for the specified host.
**endpoint**: `https://{EM.IP}/fsapi/niCore/Hosts`
**inputs**:

- *update_type* -> Type of update to perform. Options are 'update', 'delete', 'add_list_values', 'delete_list_values', 'delete_all_list_values'. _Required_
- *host_ip* -> The target host, identified by its IP address. _Required_
- *properties* -> List of properties. If `update_type` is 'update' or 'add_list_values' then it is properties and their associated values. _Required_  

**outputs**:

- *Success or Failure Message*
