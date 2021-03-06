# Advanced API Services Token Validation

This sample shows how to use the tokens generated by the "token-gen" sample in an API proxy
that utilizes both back-end services and the Advanced API Services data store.  In this sample,
a Gateway access token is validated, the Advanced API Services token is extracted, and a call
is made to Advanced API Services as a target endpoint.

This sample exposes a single endpoint, "/v1/datastore", which implements a single resource that
makes calls to "api.usergrid.com".

In general, the following steps occur:

1) The Authorization header is decoded to extract the access token.  If no access token is
	present, a 401 Unauthorized error is returned.
	
2) The access token is validated by the gateway, and a 401 Unauthorized error is returned if
	the access token is not valid.
	
3) The Advanced API Services access token - which is stored as an attribute of the Gateway 
	token - is extracted.
	
4) The call to Advanced API Services is constructed and executed, and any error is returned 
	to the calling application.

# Set up

* Import the "token-gen" sample into your system, configure it, and use it to generate 
	access tokens.  Follow the directions provided with the "token-gen" sample to learn how
	to configure the sample and generate tokens.
	
* Import this sample into your Apigee system by importing the bundle using the supplied "deploy.sh" 
script.

# Configure 

This sample does not require any additional configuration.

# Using the sample

The "invoke.sh" script provided with this sample includes commands to validate tokens and issue a
	request to Advanced API Services to retrieve the contents of the "/users" collection.

# Get help

For assistance, please use [StackOverflow](http://stackoverflow.com/tags/apigee) and add the tag "apigee".

Copyright © 2014 Apigee Corporation

Licensed under the Apache License, Version 2.0 (the "License"); you may not use
this file except in compliance with the License. You may obtain a copy
of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
