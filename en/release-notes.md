## Management > Service Monitoring > Release Notes

### Nov. 26, 2019

#### Feature Updates
* Separated transmission status information from the transmission status page. 
* Fixed the issue of broken UIs when the user language is English 
* Updated scenario editing for web monitoring 
  * Updated to show different placeholder for each text verification operator 
  * Text verification operator may be limited in exposure, depending on the [Scenario Verification Type].
  * Updated to enable **Ignore Script Errors**, **Exclude Images from Downloading**, **Activate CSS**, even for when the [Scenario Verification Type] is module. 

#### Bug Fixes  
* Fixed the issue, in which mail for [Guide for Canceling Faulty Transmission] is sent by the recipient's name, not by the user who canceled.


### August 27, 2019

#### Feature Updates
* Japanese font changed into TOAST Common Font.
* Separated input labels for IP from PORT, on the editing page of TCP monitoring scenario for better readability.

#### Bug Fixes
* Fixed the display error of time on the [View Transmission Details] page.
* Updated, for the registration of monitoring error, to register transmission title in the language set when a scenario is saved.
* Fixed the wrong notification of expiration, even if it is not expired, when you access error notification page via error transmission message
* Fixed error in which a wrong message title is added, for Japanese error transmission messages

### July 23, 2019

#### New Service Releases
Service Monitoring is a service failure management platform to allow stable service operations
	* Transmission administrator assigned for each service, to manage transmission channels
	* Supports a variety of monitoring methods - Web Monitoring, TCP Monitoring, or Batch Monitoring
