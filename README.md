# Trulioo SDK for Java - Hydrogen Fork #

## Version 1.0.9.9

### This is a fork of Trulioo SDK 1.0.2.1 intended to serve as a bridge to the new Trulioo API. Trulioo has not yet released their SDK but helped me develop this fork which adjusts the API URL and replaces Basic authentication with API Key authentication.
When Trulioo releases their matching SDK, simply update the maven pom reference and remove this package from the local maven repository named "local-maven-repo" under the project root.


### Introduction

Trulioo provides a collection of API methods to help you build business processes powered by the GlobalGateway Normalized API. The Normalized API is a loosely coupled API; fields may be added to our services and responses as the API evolves, and a client must be able to safely ignore fields and data that are not expected. The GlobalGateway Normalized API can help automate your business processes by performing the following tasks:

#### Identity Verification

Electronic identity verification (eIDV) was created specifically to help your business comply with Anti-Money Laundering (AML) and Know Your Customer (KYC) rules and has since evolved to support a diverse range of international electronic identity verification requirements.

#### Document Verification

ID Document Verification analyzes, verifies, and authenticates 3,500 different types of identity documents from nearly every country in the world. The combination of eIDV and ID Document Verification during the Customer Due Diligence check can assist your business in meeting your AML, KYC and Counter Terrorist Financing (CTF) compliance requirements.

#### Business Verification

Business Verification analyzes, verifies and provides data intelligence for business entities in 83 countries. During Customer Due Diligence, Business Verification assists clients to automate compliance workflows, reduce manual front-to- back office operations, take advantage of digital processes, decrease the risk of fraud, and allow staff to focus on key compliance considerations.

#### AML Watchlist

Global AML Watchlist helps your business comply with domestic and international AML, CTF and sanctions enforcement regulations. The watchlist covers sanction lists, law enforcements lists and governing regulatory bodies from around the world.

Below is an example of initializing the Trulioo API client and test authentication:

```java
import com.trulioo.normalizedapi.*;
import com.trulioo.normalizedapi.api.*;
import com.trulioo.normalizedapi.model.*;

//Set client here
ApiClient apiClient = new ApiClient();
apiClient.setUsername("-- USER NAME --");
apiClient.setPassword("-- PASSWORD --");

//ConnectionApi
ConnectionApi connectionClient = new ConnectionApi(apiClient);

//testAuthentication
String testResult = connectionClient.testAuthentication();
System.out.println(testResult);

//testAuthenticationAsync
connectionClient.testAuthenticationAsync(new ApiCallback<String>() {
	@Override
	public void onFailure(ApiException ae, int i, Map<String, List<String>> map) {
		Logger.getLogger(SdkJavaV1Sample.class.getName()).log(Level.SEVERE, null, ae);
	}

	@Override
	public void onSuccess(String t, int i, Map<String, List<String>> map) {
		System.out.println(t);
	}

	@Override
	public void onUploadProgress(long l, long l1, boolean bln) {
		//To change body of generated methods, choose Tools | Templates.
	}

	@Override
	public void onDownloadProgress(long l, long l1, boolean bln) {
		//To change body of generated methods, choose Tools | Templates.
	}
});

```


### Development environment

The Trulioo SDK for Java is generated by Swagger CodeGen 2.2.3

#### Java client library

##### Maven

```xml
<dependency>
	<groupId>com.trulioo</groupId>
	<artifactId>normalizedapi</artifactId>
	<version>[1.0.0,1.1.0)</version>
</dependency>
```

##### Gradle

```
compile "com.trulioo:normalizedapi:1.0.+"
```

#### Build locally

##### Requirements

* Java 7 or 8

* Apache maven 3.3.3 or higher

##### Maven

```
mvn clean package
```

##### Gradle
```
gradlew clean build
```


### Changelog

The [CHANGELOG.md](https://github.com/Trulioo/sdk-java-v1/blob/master/CHANGELOG.md) file in the root of the repository contains a description of changes for each version of the SDK.

### Documentation and resources

If you need to know more:

* For more about the Trulioo REST API V1, see the [REST API Reference](https://developer.trulioo.com/v1.0/reference).

* For starter guides, product information and best practices see the [Documentation](https://developer.trulioo.com/docs).

* For more about Trulioo in general, see [Trulioo Website](https://www.trulioo.com/).

### Support


1. You will be granted support if you or your company are already covered under an existing maintenance/support agreement. Send an email to _support@trulioo.com_ and include "Trulioo SDK for Java V1" in the subject line.

2. Trulioo will NOT provide support for the extension if the core library has been modified. We would also like to know why you modified the code please send feedback to _support@trulioo.com_

### Contact Us

You can reach via channels listed on [Trulioo website](https://www.trulioo.com/company/contact-us/)

## License

The Trulioo SDK for Java is licensed under the Apache License 2.0. Details about the license can be found in the LICENSE file. Copyright 2017 Trulioo Information Services Inc. Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0. Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.