This is a set of extractors for use within Graylog, to parse the output of
Pfsense filter logs.
# Prerequisites
#### Pfsense
##### version:Pfsense 2.6.0-RELEASE
Select Log Message Format to "syslog (RFC 5424, with RFC 3339 microsecond-precision timestamps)"
Set Remote log servers
check Remote Syslog Content


#### Graylog input
##### version: Graylog 4.2.7+879e651
Set store_full_message: true

# Installation
* Open the Graylog administrative interface
* Open the "System/Inputs" menu
* Select "Inputs"
* Select "Manage Extractors" for the input that receives Pfsense logs
* Select "Actions" menu
* Select "Import extractors"
* Paste the contents of [extractors.json](extractors.json) into the text box
* Select the button "Add extractors to input"

# Usage
* Open your Graylog search
* Search for `application_name:filterlog`
* The search results should now be showing all TCP/UDP/ICMP data as separate fields

# Background
Thank you for this repository https://github.com/facyber/pfSense-Graylog-Extractor.git
but I had to adapt to work :?

# GeoIP
Set order Message Processors Configuration in menu System/Configuraiton

N	Message Filter Chain	active
N+1	GeoIP Resolver	active
