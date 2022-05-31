[![Feature Requests](https://img.shields.io/github/issues/microsoft/vscode/feature-request.svg)](https://github.com/microsoft/vscode/issues?q=is%3Aopen+is%3Aissue+label%3Afeature-request+sort%3Areactions-%2B1-desc)
[![Bugs](https://img.shields.io/github/issues/microsoft/vscode/bug.svg)](https://github.com/microsoft/vscode/issues?utf8=✓&q=is%3Aissue+is%3Aopen+label%3Abug)
[![Gitter](https://img.shields.io/badge/chat-on%20gitter-yellow.svg)](https://gitter.im/Microsoft/vscode)
[![NetflixOSS Lifecycle](https://img.shields.io/osslifecycle/Netflix/hystrix.svg)]()
[![][travis img]][travis]
[![][maven img]][maven]
[![][license img]][license]

# Wiki Template(Product Name): Product Title(let people recognise your product)
Wiki Template is developed and maintained by Dhaka CT Team. 

A brief introduction of product needs to be present here.

[Example or Scenario](https://github.com/facebook/rocksdb/tree/main/examples) can be shared through link here.

See the github [Wiki](https://github.com/JannatRuma/Wiki_Template/wiki) for full documentation, examples, operational details and other information.

See the [Javadoc](http://netflix.github.com/Hystrix/javadoc) for the API.

## Build

To build:

```
$ git clone git@github.com:Netflix/Hystrix.git
$ cd Hystrix/
$ ./gradlew build
```

Futher details on building can be found on the [Getting Started](https://github.com/Netflix/Hystrix/wiki/Getting-Started) page of the wiki.

## Run Demo

To run a [demo app](https://github.com/Netflix/Hystrix/tree/master/hystrix-examples/src/main/java/com/netflix/hystrix/examples/demo/HystrixCommandDemo.java) do the following:

```
$ git clone git@github.com:Netflix/Hystrix.git
$ cd Hystrix/
./gradlew runDemo
```

You will see output similar to the following:

```
Request => GetUserAccountCommand[SUCCESS][8ms], GetPaymentInformationCommand[SUCCESS][20ms], GetUserAccountCommand[SUCCESS, RESPONSE_FROM_CACHE][0ms]x2, GetOrderCommand[SUCCESS][101ms], CreditCardCommand[SUCCESS][1075ms]
Request => GetUserAccountCommand[FAILURE, FALLBACK_SUCCESS][2ms], GetPaymentInformationCommand[SUCCESS][22ms], GetUserAccountCommand[FAILURE, FALLBACK_SUCCESS, RESPONSE_FROM_CACHE][0ms]x2, GetOrderCommand[SUCCESS][130ms], CreditCardCommand[SUCCESS][1050ms]
Request => GetUserAccountCommand[FAILURE, FALLBACK_SUCCESS][4ms], GetPaymentInformationCommand[SUCCESS][19ms], GetUserAccountCommand[FAILURE, FALLBACK_SUCCESS, RESPONSE_FROM_CACHE][0ms]x2, GetOrderCommand[SUCCESS][145ms], CreditCardCommand[SUCCESS][1301ms]
Request => GetUserAccountCommand[SUCCESS][4ms], GetPaymentInformationCommand[SUCCESS][11ms], GetUserAccountCommand[SUCCESS, RESPONSE_FROM_CACHE][0ms]x2, GetOrderCommand[SUCCESS][93ms], CreditCardCommand[SUCCESS][1409ms]

#####################################################################################
# CreditCardCommand: Requests: 17 Errors: 0 (0%)   Mean: 1171 75th: 1391 90th: 1470 99th: 1486 
# GetOrderCommand: Requests: 21 Errors: 0 (0%)   Mean: 100 75th: 144 90th: 207 99th: 230 
# GetUserAccountCommand: Requests: 21 Errors: 4 (19%)   Mean: 8 75th: 11 90th: 46 99th: 51 
# GetPaymentInformationCommand: Requests: 21 Errors: 0 (0%)   Mean: 18 75th: 21 90th: 24 99th: 25 
#####################################################################################

Request => GetUserAccountCommand[SUCCESS][10ms], GetPaymentInformationCommand[SUCCESS][16ms], GetUserAccountCommand[SUCCESS, RESPONSE_FROM_CACHE][0ms]x2, GetOrderCommand[SUCCESS][51ms], CreditCardCommand[SUCCESS][922ms]
Request => GetUserAccountCommand[SUCCESS][12ms], GetPaymentInformationCommand[SUCCESS][12ms], GetUserAccountCommand[SUCCESS, RESPONSE_FROM_CACHE][0ms]x2, GetOrderCommand[SUCCESS][68ms], CreditCardCommand[SUCCESS][1257ms]
Request => GetUserAccountCommand[SUCCESS][10ms], GetPaymentInformationCommand[SUCCESS][11ms], GetUserAccountCommand[SUCCESS, RESPONSE_FROM_CACHE][0ms]x2, GetOrderCommand[SUCCESS][78ms], CreditCardCommand[SUCCESS][1295ms]
Request => GetUserAccountCommand[FAILURE, FALLBACK_SUCCESS][6ms], GetPaymentInformationCommand[SUCCESS][11ms], GetUserAccountCommand[FAILURE, FALLBACK_SUCCESS, RESPONSE_FROM_CACHE][0ms]x2, GetOrderCommand[SUCCESS][153ms], CreditCardCommand[SUCCESS][1321ms]
```

This demo simulates 4 different [HystrixCommand](https://github.com/Netflix/Hystrix/tree/master/hystrix-core/src/main/java/com/netflix/hystrix/HystrixCommand.java) implementations with failures, latency, timeouts and duplicate calls in a multi-threaded environment.

It logs the results of [HystrixRequestLog](https://github.com/Netflix/Hystrix/tree/master/hystrix-core/src/main/java/com/netflix/hystrix/HystrixRequestLog.java) and metrics from [HystrixCommandMetrics](https://github.com/Netflix/Hystrix/tree/master/hystrix-core/src/main/java/com/netflix/hystrix/HystrixCommandMetrics.java).

## Dashboard

The hystrix-dashboard component of this project has been deprecated and moved to [Netflix-Skunkworks/hystrix-dashboard](https://github.com/Netflix-Skunkworks/hystrix-dashboard). Please see the README there for more details including important security considerations.


## Bugs and Feedback

For bugs, questions and discussions please use the [GitHub Issues](https://github.com/Netflix/Hystrix/issues).


Questions and discussions are welcome on the [RocksDB Developers Public](https://www.facebook.com/groups/rocksdb.dev/) Facebook group and [email list](https://groups.google.com/g/rocksdb) on Google Groups.


## Code of Conduct

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## License

Copyright (c) Microsoft Corporation. All rights reserved.

Licensed under the [MIT](LICENSE.txt) license.
