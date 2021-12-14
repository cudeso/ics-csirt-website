---
layout: news
title:  Siemens Advisory (SSA-661247)
subtitle: SSA-661247 Apache Log4j Vulnerability (CVE-2021-44228, Log4Shell) 
date:   2021-12-13
category: protect detect respond
author: cudeso
---
Siemens released their advisory for the log4j vulnerability.

[https://cert-portal.siemens.com/productcert/pdf/ssa-661247.pdf](https://cert-portal.siemens.com/productcert/pdf/ssa-661247.pdf)


Siemens has identified the following specific workarounds and mitigations that customers can apply to
reduce the risk:
- If the specific Siemens product (which is currently using Log4j versions >= 2.10 and < 2.15.0 in its versions released so far) allows it: Set the parameter log4j2.formatMsgNoLookups to ‘true’. The two most common options to set this parameter in the Java Virtual Machine are: as cmdline parameter (‘-Dlog4j2 formatMsgNoLookups=true’) or as environment variable
(‘LOG4J_FORMAT_MSG_NO_LOOKUPS=”true”’).
- If the specific Siemens product (which is currently using Log4j versions 2.0-beta9 to 2.10.0 in its versions released so far) allows it: Remove the JndiLookup class from the classpath: ’zip -q -d
log4j-core-*.jar org/apache/logging/log4j/core/lookup/JndiLookup.class’
- If the specific Siemens product (which is currently using Log4j versions >=2.7 and <2.15.0 in its versions released so far) allows it: Modify all PatternLayout patterns to specify the message converter as ‘%m{nolookups}’ instead of just ‘%m’.
- If the specific Siemens product allows it: Update the Log4j component to 2.15.0 or later versions on the systems where the product is installed.