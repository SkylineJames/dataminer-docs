---
uid: General_Main_Release_10.4.0_CU4
---

# General Main Release 10.4.0 CU4 - Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

> [!TIP]
> For information on how to upgrade DataMiner, see [Upgrading a DataMiner Agent](xref:Upgrading_a_DataMiner_Agent).

### Enhancements

#### Security enhancements [ID_38263] [ID_39611]

<!-- 38263: MR 10.3.0 [CU16]/10.4.0 [CU4] - FR 10.4.3 -->
<!-- 39611: MR 10.3.0 [CU16]/10.4.0 [CU4] - FR 10.4.7 -->

A number of security enhancements have been made.

#### Cassandra & Cassandra cluster: Enhanced performance when querying the maskstate table [ID_39192]

<!-- MR 10.3.0 [CU16]/10.4.0 [CU4] - FR 10.4.7 -->

Because of a number of enhancements, on systems using a Cassandra and Cassandra cluster database, overall performance has increased when querying the maskstate database table. As a result, elements will start up quicker depending on the number of masked objects in the database.

#### Service & Resource Management: Enhanced performance when creating multiple bookings simultaneously [ID_39390]

<!-- MR 10.3.0 [CU16]/10.4.0 [CU4] - FR 10.4.7 -->

Because of a number of enhancements, overall performance has increased when creating multiple bookings simultaneously.

#### DataMiner Object Models: Enhanced performance of DOM instance count queries with a DOM state filter [ID_39405]

<!-- MR 10.4.0 [CU4] - FR 10.4.7 -->

Because of a number of enhancements, overall performance has increased when executing a DOM instance count query with a DOM state filter.

#### SLAnalytics: Enhanced alarm template monitoring [ID_39561]

<!-- MR 10.4.0 [CU4] - FR 10.4.7 -->

When an alarm template contained multiple lines for the same parameter, each with a different filter, up to now, SLAnalytics would only take into account the lines that were being monitored. From now on, as soon as one line related to a specific parameter is being monitored, SLAnalytics will take into account all lines related to that parameter.

### Fixes

#### Issues with user accounts [ID_39234]

<!-- MR 10.4.0 [CU4] - FR 10.4.7 -->

In some cases, user accounts could become corrupted and group memberships could get lost.

Also, in some cases, SLDataMiner could stop working when an alarm template or trend template was uploaded, removed, assigned or unassigned.

#### SLNet: Problem when sending messages due to an issue with the protobuf serializers [ID_39275]

<!-- MR 10.3.0 [CU16]/10.4.0 [CU4] - FR 10.4.7 -->

When SLNet sent a message, in some cases, an error could occur due to an issue with the protobuf serializers.

#### Problem with SLNet when information on hanging calls was being retrieved [ID_39373]

<!-- MR 10.3.0 [CU16]/10.4.0 [CU4] - FR 10.4.7 -->

In some rare cases, an error could occur in SLNet when information on hanging calls was being retrieved.

#### SLSNMPAgent would incorrectly interpret variable trap bindings of type 'IpAddress' as bindings of type 'OctetString' [ID_39425]

<!-- MR 10.3.0 [CU16]/10.4.0 [CU4] - FR 10.4.7 -->

Up to now, SLSNMPAgent would incorrectly interpret variable trap bindings of type 'IpAddress' as bindings of type 'OctetString'.

#### Protocols: 'next' attribute would no longer work for SNMP parameters [ID_39430]

<!-- MR 10.3.0 [CU16]/10.4.0 [CU4] - FR 10.4.7 -->

The `next` attribute of a parameter inside a parameter group determines the number of milliseconds DataMiner has to wait before reading the next parameter. This functionality no longer worked for SNMP parameters.

Also, when a group contained single parameters in combination with a partial table, the single parameters would incorrectly also be requested each time the next batch of rows were requested from the partial table. From now on, the single parameters will only be requested once.

> [!NOTE]
> When a `next` attribute is defined on a partial SNMP table parameter inside a parameter group, then the delay will also be applied between the batches of rows that are requested.

#### Interactive Automation script was not able to continue once a lost connection was re-established [ID_39487]

<!-- MR 10.3.0 [CU16]/10.4.0 [CU4] - FR 10.4.7 -->

When a client application lost connection while an interactive Automation script was being run, up to now, the script would stop as it was not able to continue once the connection was re-established.

From now on, when a client application loses connection while an interactive Automation script is being run, the script will continue once the connection is re-established.
