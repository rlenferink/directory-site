---
title: Fortress Overview
---

# Apache Fortress Overview

FORTRESS is a standards-based authorization system, that provides role-based access control, delegated administration and password policy services using an LDAP backend.

## What's in it?  

Included are the following components:

* Core  - Java Authorization SDK
* Realm - Java EE security for Apache Tomcat
* Rest  - HTTP protocol wrappers for the APIs using Apache CXF
* Web   - HTML pages and framework for the APIs using Apache Wicket

It's released under terms of the Apache License 2.0. 

## How Does It Work?

Fortress is a Role-Based Access Control security system.  It uses a directory server to store the information about users, roles, permissions, etc.  Out-of-the-box it supports either ApacheDS or OpenLDAP servers but works with any LDAPv3 compliant system.

To learn how to install, setup and configure with either of the supported servers, check out the quickstarts:

* [QUICKSTARTS](installation.html)

## Other Guides

### API usage
Probably the best place to start is the javadoc.  To understand how RBAC works, look at the interfaces like AccessMgr, AdminMgr and ReviewMgr.  For ARBAC add 'Del' to the name - for delegated.  DelAdminMgr, DelAccessMgr, etc.  For password policies, PwPolicyMgr.

### Configuration
Next is to understand how the runtime works.  As you might expect, Fortress requires a large number of parameters that bind it to a runtime environment.  For example the LDAP server's coordinates, hostname, port, suffix, service account credentials and more.  The configuration subsystem pulls these parameters from a variety of locations.

* [README-CONFIG.md](https://github.com/apache/directory-fortress-core/blob/master/README-CONFIG.md) - How the Fortress Config subsystem works

### Multitenancy
The Fortress APIs and data storage is fully multitenant.  To understand how that works.

* [README-MULTITENANCY.md](https://github.com/apache/directory-fortress-core/blob/master/README-MULTITENANCY.md) - How Fortress Multitenancy works

## What technologies at play?

Fortress products run on open system hardware and software platforms supporting LDAPv3, HTTP & Java.  

## What standards apply?

The following standards are implemented...

### ANSI Role-Based Access Control (INCITS 359) 

There is more to RBAC than assigning users to groups and applying ACL policies within directories or databases.  [RBAC](http://csrc.nist.gov/groups/SNS/rbac/documents/draft-rbac-implementation-std-v01.pdf) systems provide selective Role activation/deactivation, role hierarchies, and constraints over separation of duty.  The [RBAC](http://csrc.nist.gov/groups/SNS/rbac/documents/draft-rbac-implementation-std-v01.pdf) component provides APIs to add, update, delete, and search the directory data

More info can be found on [Intro to ANSI RBAC Page](user-guide/1-intro-rbac.html)

### [Java EE Platform](http://java.net/projects/javaee-spec/pages/Home) (tm) Security

Used for SSL, X.509 mutual authentication, form-based container authentication, authorization and SSO.  Works within compliant Java Web apps like Fortress Rest and Web.  

### Administrative Role-Based Access Control ([ARBAC02](http://profsandhu.com/journals/tissec/p113-oh.pdf))

The ARBAC model explains how [RBAC](http://csrc.nist.gov/groups/SNS/rbac/documents/draft-rbac-implementation-std-v01.pdf) can be extended with organizational controls to govern policies regarding the security administration process. ARBAC helps by allowing administrative tasks be delegated to end users who fall outside typical datacenter operations. 

### IETF Password Policies

Fortress fully supports password policies of both ApacheDS and OpenLDAP.  It adds by integrating with its administrative and access control APIs.  These APIs enable outside apps to participate and manipulate OpenLDAP password policies without understanding the specifics of how they work. Fortress provides services for setting up new policies and ensuring password policies are tracked and enforced across all avenues.

### Auditing

Fortress audits use OpenLDAP's slapd access log overlay.

The Fortress audits rely on slapd events to track its data exchanges performed within its own APIs.  Change event tracking includes adds, updates, and deletes of Fortress entities.  Read and search events tracked include user authentication, authorization, and policy interrogations.  Full historical data change tracking is maintained and may be searched later with APIs to be used for monitoring, reporting, and undo. The log may be retrieved later to synch with outside database for long-term regulatory and compliance concerns.  

### Temporal Constraints 

The Fortress Temporal model allows Users and Roles to carry time and date Constraints which govern when activations may occur. Role constraints are checked on every call into Fortress.  The user constraint applied only at session creation.

### ANSI RBAC Policy-Enhanced (INCITS-494-2012)

One day.

## What services are available?

Over one hundred services divided across the Manager components.

A description of these managers follow along with their associated javadoc links that describe the apis...

###RBAC Managers

* [AccessMgr.html](https://directory.apache.org/fortress/gen-docs/latest/apidocs/org/apache/directory/fortress/core/AccessMgr.html) - Performs runtime access control operations on objects that are provisioned RBAC entities that reside in LDAP directory.
* [AdminMgr.html](https://directory.apache.org/fortress/gen-docs/latest/apidocs/org/apache/directory/fortress/core/AdminMgr.html) - Performs administrative functions to provision Fortress RBAC entities into the LDAP directory.
* [ReviewMgr.html](https://directory.apache.org/fortress/gen-docs/latest/apidocs/org/apache/directory/fortress/core/ReviewMgr.html) - The review functions on RBAC entities in LDAP.

###ARBAC Managers

* [DelAccessMgr.html](https://directory.apache.org/fortress/gen-docs/latest/apidocs/org/apache/directory/fortress/core/DelAccessMgr.html) - Runtime delegated access control operations on objects that are provisioned Fortress ARBAC entities that reside in LDAP.
* [DelAdminMgr.html](https://directory.apache.org/fortress/gen-docs/latest/apidocs/org/apache/directory/fortress/core/DelAdminMgr.html) - Policy administration of Fortress ARBAC entities in LDAP.
* [DelReviewMgr.html](https://directory.apache.org/fortress/gen-docs/latest/apidocs/org/apache/directory/fortress/core/DelReviewMgr.html) - Policy review ops of ARBAC entities in LDAP.

###PW Policies Manager

* [PwPolicyMgr.html](https://directory.apache.org/fortress/gen-docs/latest/apidocs/org/apache/directory/fortress/core/PwPolicyMgr.html) - Used to perform admin and review functions on the PWPOLICIES data sets.

###Audit Manager

* [AuditMgr.html](https://directory.apache.org/fortress/gen-docs/latest/apidocs/org/apache/directory/fortress/core/AuditMgr.html) - Methods used to search OpenLDAP's slapd access log for fortress events.

###Config Manager

* [ConfigMgr.html](https://directory.apache.org/fortress/gen-docs/latest/apidocs/org/apache/directory/fortress/core/ConfigMgr.html) - CRUD methods used to manage properties stored within LDAP.

## Where is it?

Source is managed by Apache's GIT repo:

* [Fortress Core](https://gitbox.apache.org/repos/asf/directory-fortress-core.git)
* [Fortress Web](https://gitbox.apache.org/repos/asf/directory-fortress-commander.git)
* [Fortress Rest](https://gitbox.apache.org/repos/asf/directory-fortress-enmasse.git)
* [Fortress Realm](https://gitbox.apache.org/repos/asf/directory-fortress-realm.git)
