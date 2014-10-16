---
layout: default-devplatform
permalink: /als/v1/user/deploy/languages/java/
---
<!--UNDER REVISION-->

#Developing in Java[](#java "Permalink to this headline")

Whether you're deploying an application to the HP Helion Development Platform, a Cloud Foundry based Platform as a Service (PaaS), or writing applications that take advantage of HP Helion OpenStack® to manage infrastructure or software services, tools to enable successful development are available in Java.

For more information on working with object storage, 
see the [HP Helion OpenStack® Object Storage Service Overview](/helion/openstack/services/object/overview/).

For information about authentication, see [Authenticating with Access Key and Token](/als/v1/user/deploy/languages/java/authentication/).

For more help with building applications, see the Java [Framework](/als/v1/user/deploy/languages/java/frameworks) or [Buildpack](/als/v1/user/deploy/buildpack/#buildpacks) reference.  Supported frameworks include Java Web, Spring, and
Java EE (via TomEE or JBoss)<!--, Grails, and Lift-->.

## Using JDBC[](#using-jdbc "Permalink to this headline")

It is possible to access the database services using the standard JDBC
API:

    String helion_services = System.getenv("VCAP_SERVICES");
    String hostname = NULL_STRING;
    String dbname = NULL_STRING;
    String user = NULL_STRING;
    String password = NULL_STRING;
    String port = NULL_STRING;

    if (helion_services != null && helion_services.length() > 0) {
      try
      {
        JsonRootNode root = new JdomParser().parse(helion_services);

        JsonNode credentials = root.getNode("mysql");

        dbname = credentials.getStringValue("name");
        hostname = credentials.getStringValue("hostname");
        user = credentials.getStringValue("user");
        password = credentials.getStringValue("password");
        port = credentials.getNumberValue("port");

        String dbUrl = "jdbc:mysql://" + hostname + ":" + port + "/" + dbname;

        Class.forName("com.mysql.jdbc.Driver");
        Connection connection = DriverManager.getConnection(dbUrl, user, password);
        return connection;

      }
      catch (Exception e)
      {
        throw new SQLException(e);
      }
    }

### Example[](#example "Permalink to this headline")

The [Java database sample](/helion/devplatform/workbook/messaging/java/) sample
demonstrates a simple Java application using a MySQL service.



CATALINA\_OPTS[](#catalina-opts "Permalink to this headline")
--------------------------------------------------------------

The CATALINA\_OPTS environment variable can be set in the
`env:` block of manifest.yml (or set in the
Management Console) to override Application Lifecycle Service defaults.

**Note**

CATALINA\_OPTS settings cannot be modified without restaging.
Applications must be re-pushed with new settings to apply changes.

Application Lifecycle Service sets the CATALINA\_OPTS environment variable for applications
using Tomcat automatically, based on the `mem:`
value specified for application instances. Application Lifecycle Service will always leave at
least 64MB for the heap, but will otherwise reserves up to 96MB for
overhead, that is for the code of the JVM itself, for additional
libraries loaded via JNI, for additional processes to run in the
background, and for the JVM permanent pool.

This means, for example, a 128MB application will end up with 64MB for
the heap and 64MB for overhead, a 160MB application will still have 64MB
for the heap but 96MB for overhead, and a 512MB application will get a
416MB heap and allow 96MB for overhead.

####OpenStack trademark attribution
*The OpenStack Word Mark and OpenStack Logo are either registered trademarks/service marks or trademarks/service marks of the OpenStack Foundation, in the United States and other countries and are used with the OpenStack Foundation's permission. We are not affiliated with, endorsed or sponsored by the OpenStack Foundation, or the OpenStack community.*