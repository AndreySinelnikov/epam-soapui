

GOAL: Start a SOAP project

1. Choose WSDL at startup, SoapUI will generate interface definition from it.

NOTE: In WSDL, "element" tag contains method/operation name.

--------

GOAL: Add suite and tests

1. Right-click the root directory, choose to add a new suite.
2. Suite can be edited (ie with setup/teardown scripts).
3. Right-click the suite directory, choose to add a test to suite.
4. Test can be edited (ie with setup/teardown scripts). Scripts can be written in Groovy or Java.

--------

GOAL: Add an Xpath-based assertion to a test step

1. IN Step details, ADD assertion with Property Content -> Xpath Match.
2. IN Declare tab of the assertion, ADD "declare namespace {namespace_name}={url};" (URL gotten from SOAP response, tagged as "xmlns")
3. IN Declare tab, ADD "//{namespace_name}:{tag_name}" to access contents of a specified tag.
4. IN Expected Result tab, ADD the expected content value.

--------

GOAL: Use values from Step level properties in a test

1. IN Steps, ADD Property step before a step that uses these properties.    Properties could be loaded from an external file.
2. IN a request/assertion step, ADD property name within brackets in "${}".

-------

GOAL: Use values from System/Project/Suite/Case level properties in a test

1. IN a request/assertion step, ADD "${}".
2. IN the brackets, TYPE "#System|#Project|#TestSuite|#TestCase", then "#",
   then property name.

-------

GOAL: Send values from one response to another request

1. IN test steps, ADD two requests.
2. IN between these steps, ADD Property Transfer step.
3. IN Property Transfer step, ADD transfer.
4. IN transfer, ADD Source response and Target request. Click "ns" button.
5. IN Source and Target tabs, ADD transferred elements' Xpaths. Use
   //*[name()='namespace:tag']/*[name()='tag'] hack to avoid namespace-related hassle.

-------







