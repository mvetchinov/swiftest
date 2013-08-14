swiftest
========

The CLI utilities for Swift installation testing


## How to run? 

Fill your swift parameters into the `settings` file:

    export SW_URL=http://192.168.122.10:8080/auth/v1.0
    export SW_VERSION=1.0
    export SW_TENANT=test
    export SW_USER=tester
    export SW_PWD=testing
 
    export SWIFT="swift  -V ${SW_VERSION} -A ${SW_URL} -U ${SW_TENANT}:${SW_USER} -K ${SW_PWD}"
    #export SWIFT="swift -A http://192.168.122.10:8080/auth/v1.0  -U test:tester -K testing"


Clean your swift account: 

    # ./delete.sh

Run to create and upload a testing set of data to swift (will create 2 containers with ~1000 objects each):

    # ./create.sh

Run to start checking. This script upload the data from swift and compare it with previously uploaded data:

    # ./check.sh
    .....
    .....
    container2/pA [headers 0.026s, total 0.026s, 0.000s MB/s]
    container2/aA [headers 0.019s, total 0.019s, 0.000s MB/s]
    container2/mA [headers 0.014s, total 0.014s, 0.001s MB/s]
    container2/qA [headers 0.012s, total 0.012s, 0.001s MB/s]
    TEST OK

The result of test is in the last line of the output. There are two variants: "TEST OK" or "TEST FAILED"

For cleaning up of your swift account and local temporary data run:

    # ./delete.sh
 
