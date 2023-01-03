# X-Road Load Tests

X-Road loadtest scripts used for testing Palveluväylä are stored here. More details from scripts can be found from project [Wiki pages](https://github.com/vrk-kpa/xroad-load-tests/wiki).


# xoad-load-tests
>XRoad load tests

>Variables in the script
>${host} 					        host 					        Host of webservice (servername.fi)
>${loopcount} 			        loopcount				      How many times test is run
>${portno}    			        portno					      Port of service		(80, 8080 etc.)
>${rampup}					        rampup 					      Ramp up users	
>${threads}				        threads					      How many treats
>${MemberName}			        MemberName				    Customer ID		()
>${MemberClass} 			      MemberClass				    CustomerClass  	(GOV, ORG etc..)
>${MemberCode}				      MemberCode				    CustomerCode	(123456-7 ....) can be found from security server config
>${Subsystemcode_client} 	Subsystemcode_client 	Subsystemcode client
>${Subsystemcode_service} 	Subsystemcode_service Subsystemcode service
>${path} 					        path					        End path of the servername (test-service-0.0.1/Endpoint)
>${Instance} 				      Instance  				    X Road Instance
>${timer}	 				        timer 					      timer
>${timeout} 					      timeout 				      Timeout value
>${loadsoftoken} 			    loadsoftoken 			    Loadsofia token

In tests were used testservice https://github.com/petkivim/x-road-test-service. More detais from it can be found from this pages
´´´ xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:id="http://x-road.eu/xsd/identifiers" xmlns:xrd="http://x-road.eu/xsd/xroad.xsd">
    <SOAP-ENV:Header>
        <xrd:client id:objectType="SUBSYSTEM">														// instance sending request
            <id:xRoadInstance>FI-DEV</id:xRoadInstance>										// ${Instance}
            <id:memberClass>GOV</id:memberClass>													// ${MemberClass}
            <id:memberCode>123456-7</id:memberCode>												// ${MemberCode} 	${MemberCode_1} might be needed
            <id:subsystemCode>TestClient</id:subsystemCode>								// ${Subsystemcode_client}
        </xrd:client>
        <xrd:service id:objectType="SERVICE">														  // instance responding
            <id:xRoadInstance>FI-DEV</id:xRoadInstance>										// ${Instance} (FI-DEV, FI-TEST etc.)
            <id:memberClass>GOV</id:memberClass>													// ${MemberClass}	(GOV, ORG etc)
            <id:memberCode>0245437-2</id:memberCode>											// ${MemberCode}	${MemberCode_2} might be needed
            <id:subsystemCode>TestService</id:subsystemCode>							// ${Subsystemcode_service}
            <id:serviceCode>testService</id:serviceCode>												
            <id:serviceVersion>v1</id:serviceVersion>
        </xrd:service>
        <xrd:userId>test</xrd:userId>
        <xrd:id>ID11234</xrd:id>
        <xrd:protocolVersion>4.0</xrd:protocolVersion>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:testService xmlns:ns1="http://test.x-road.fi/producer">
            <ns1:request>
                <ns1:responseBodySize>25</ns1:responseBodySize>						  // responce Body size
                <ns1:responseAttachmentSize>0</ns1:responseAttachmentSize>  // responce Attachment size
            </ns1:request>
        </ns1:testService>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

´´´