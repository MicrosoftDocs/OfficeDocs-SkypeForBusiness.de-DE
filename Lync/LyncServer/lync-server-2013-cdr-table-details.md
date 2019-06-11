---
title: 'Lync Server 2013: Ausführliche Informationen zur CDR-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f87e681cc25f9ed64509ff3bdb31abc5fd77101d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a>Ausführliche Informationen zur CDR-Tabelle in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

In den folgenden Themen werden die Spalten in den Datenbankschema Tabellen für den Anruf Detaildatensatz (CDR) detailliert beschrieben.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Application-Tabelle in Lync Server 2013](lync-server-2013-application-table.md)

  - [CallPriorities-Tabelle in Lync Server 2013](lync-server-2013-callpriorities-table.md)

  - [CallType-Tabelle in Lync Server 2013](lync-server-2013-calltype-table.md)

  - [ClientVersions-Tabelle in Lync Server 2013](lync-server-2013-clientversions-table.md)

  - [ConferenceJoinTimeThresholds-Tabelle in lync Server 2013](lync-server-2013-conferencejointimethresholds-table.md)

  - [ConferenceMessageCount-Tabelle in Lync Server 2013](lync-server-2013-conferencemessagecount-table.md)

  - [Conferences-Tabelle in Lync Server 2013](lync-server-2013-conferences-table.md)

  - [ConferenceSessionDetails-Tabelle in Lync Server 2013](lync-server-2013-conferencesessiondetails-table.md)

  - [ConferenceUris-Tabelle in Lync Server 2013](lync-server-2013-conferenceuris-table.md)

  - [ContentTypes-Tabelle in Lync Server 2013](lync-server-2013-contenttypes-table.md)

  - [DeRegisterType-Tabelle in Lync Server 2013](lync-server-2013-deregistertype-table.md)

  - [Devices-Tabelle in Lync Server 2013](lync-server-2013-devices-table.md)

  - [Dialogs-Tabelle in Lync Server 2013](lync-server-2013-dialogs-table.md)

  - [EdgeServers-Tabelle in Lync Server 2013](lync-server-2013-edgeservers-table.md)

  - [ErrorCategory-Tabelle in lync Server 2013](lync-server-2013-errorcategory-table.md)

  - [ErrorDef-Tabelle in Lync Server 2013](lync-server-2013-errordef-table.md)

  - [ErrorReport-Tabelle in Lync Server 2013](lync-server-2013-errorreport-table.md)

  - [FileTransfers-Tabelle in Lync Server 2013](lync-server-2013-filetransfers-table.md)

  - [FocusJoinsAndLeaves-Tabelle in Lync Server 2013](lync-server-2013-focusjoinsandleaves-table.md)

  - [Frontend-Tabelle in lync Server 2013](lync-server-2013-frontend-table.md)

  - [Gateways-Tabelle in Lync Server 2013](lync-server-2013-gateways-table.md)

  - [HardwareVersions-Tabelle in Lync Server 2013](lync-server-2013-hardwareversions-table.md)

  - [IMReportSummary-Tabelle in lync Server 2013](lync-server-2013-imreportsummary-table.md)

  - [Locations-Tabelle in Lync Server 2013](lync-server-2013-locations-table.md)

  - [Manufacturers-Tabelle in Lync Server 2013](lync-server-2013-manufacturers-table.md)

  - [McuJoinsAndLeaves-Tabelle in Lync Server 2013](lync-server-2013-mcujoinsandleaves-table.md)

  - [Mcus-Tabelle in Lync Server 2013](lync-server-2013-mcus-table.md)

  - [Media-Tabelle in Lync Server 2013](lync-server-2013-media-table.md)

  - [MediaList-Tabelle in Lync Server 2013](lync-server-2013-medialist-table.md)

  - [MediationServers-Tabelle in Lync Server 2013](lync-server-2013-mediationservers-table.md)

  - [MSMQProcessing-Tabelle in lync Server 2013](lync-server-2013-msmqprocessing-table.md)

  - [Phones-Tabelle in Lync Server 2013](lync-server-2013-phones-table.md)

  - [Pools-Tabelle in Lync Server 2013](lync-server-2013-pools-table.md)

  - [ProgressReport-Tabelle in Lync Server 2013](lync-server-2013-progressreport-table.md)

  - [PurgeSettings-Tabelle in lync Server 2013](lync-server-2013-purgesettings-table.md)

  - [Registration-Tabelle in Lync Server 2013](lync-server-2013-registration-table.md)

  - [Roles-Tabelle in Lync Server 2013](lync-server-2013-roles-table.md)

  - [Servers-Tabelle in Lync Server 2013](lync-server-2013-servers-table.md)

  - [SessionDetails-Tabelle in Lync Server 2013](lync-server-2013-sessiondetails-table.md)

  - [SIPResponseMetaData-Tabelle in lync Server 2013](lync-server-2013-sipresponsemetadata-table.md)

  - [Tabelle "Syndikator" in lync Server 2013](lync-server-2013-syndicators-table.md)

  - [SyndicatorsTenantMap-Tabelle in lync Server 2013](lync-server-2013-syndicatorstenantmap-table.md)

  - [Aufgaben Tabelle in lync Server 2013](lync-server-2013-task-table.md)

  - [Tenants-Tabelle in Lync Server 2013](lync-server-2013-tenants-table.md)

  - [UriTypes-Tabelle in Lync Server 2013](lync-server-2013-uritypes-table.md)

  - [Users-Tabelle in Lync Server 2013](lync-server-2013-users-table.md)

  - [UserAgentDef-Tabelle in lync Server 2013](lync-server-2013-useragentdef-table.md)

  - [UserStatistics-Tabelle in lync Server 2013](lync-server-2013-userstatistics-table.md)

  - [VoipDetails-Tabelle in Lync Server 2013](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

