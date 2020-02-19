---
title: 'Lync Server 2013: Details zur CdR-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcb8d75948f1b85257f0182d571ea2fe08f3a0d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a>Details zur KDS-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-18_

In den folgenden Themen werden die Spalten in den einzelnen KDS-Daten Satz Tabellen (Call Detail Records) detailliert beschrieben.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Anwendungstabelle in lync Server 2013](lync-server-2013-application-table.md)

  - [CallPriorities-Tabelle in lync Server 2013](lync-server-2013-callpriorities-table.md)

  - [CallType-Tabelle in lync Server 2013](lync-server-2013-calltype-table.md)

  - [Client Versions-Tabelle in lync Server 2013](lync-server-2013-clientversions-table.md)

  - [ConferenceJoinTimeThresholds-Tabelle in lync Server 2013](lync-server-2013-conferencejointimethresholds-table.md)

  - [ConferenceMessageCount-Tabelle in lync Server 2013](lync-server-2013-conferencemessagecount-table.md)

  - [Konferenz Tabelle in lync Server 2013](lync-server-2013-conferences-table.md)

  - [ConferenceSessionDetails-Tabelle in lync Server 2013](lync-server-2013-conferencesessiondetails-table.md)

  - [ConferenceUris-Tabelle in lync Server 2013](lync-server-2013-conferenceuris-table.md)

  - [ContentTypes-Tabelle in lync Server 2013](lync-server-2013-contenttypes-table.md)

  - [Deregistertype-Tabelle in lync Server 2013](lync-server-2013-deregistertype-table.md)

  - [Devices-Tabelle in lync Server 2013](lync-server-2013-devices-table.md)

  - [Dialogfelder (Tabelle) in lync Server 2013](lync-server-2013-dialogs-table.md)

  - [EdgeServers-Tabelle in lync Server 2013](lync-server-2013-edgeservers-table.md)

  - [ErrorCategory-Tabelle in lync Server 2013](lync-server-2013-errorcategory-table.md)

  - [ErrorDef-Tabelle in lync Server 2013](lync-server-2013-errordef-table.md)

  - [ErrorReport-Tabelle in lync Server 2013](lync-server-2013-errorreport-table.md)

  - [Filetransfers-Tabelle in lync Server 2013](lync-server-2013-filetransfers-table.md)

  - [FocusJoinsAndLeaves-Tabelle in lync Server 2013](lync-server-2013-focusjoinsandleaves-table.md)

  - [Frontend-Tabelle in lync Server 2013](lync-server-2013-frontend-table.md)

  - [Gateways-Tabelle in lync Server 2013](lync-server-2013-gateways-table.md)

  - [Hardware Versions-Tabelle in lync Server 2013](lync-server-2013-hardwareversions-table.md)

  - [IMReportSummary-Tabelle in lync Server 2013](lync-server-2013-imreportsummary-table.md)

  - [Tabelle "Locations" in lync Server 2013](lync-server-2013-locations-table.md)

  - [Herstellertabelle in lync Server 2013](lync-server-2013-manufacturers-table.md)

  - [McuJoinsAndLeaves-Tabelle in lync Server 2013](lync-server-2013-mcujoinsandleaves-table.md)

  - [Tabelle "MCU" in lync Server 2013](lync-server-2013-mcus-table.md)

  - [Medientabelle in lync Server 2013](lync-server-2013-media-table.md)

  - [Medialist-Tabelle in lync Server 2013](lync-server-2013-medialist-table.md)

  - [MediationServers-Tabelle in lync Server 2013](lync-server-2013-mediationservers-table.md)

  - [MSMQProcessing-Tabelle in lync Server 2013](lync-server-2013-msmqprocessing-table.md)

  - [Phones-Tabelle in lync Server 2013](lync-server-2013-phones-table.md)

  - [Tabelle "Pools" in lync Server 2013](lync-server-2013-pools-table.md)

  - [ProgressReport-Tabelle in lync Server 2013](lync-server-2013-progressreport-table.md)

  - [PurgeSettings-Tabelle in lync Server 2013](lync-server-2013-purgesettings-table.md)

  - [Registrierungstabelle in lync Server 2013](lync-server-2013-registration-table.md)

  - [Tabelle "Roles" in lync Server 2013](lync-server-2013-roles-table.md)

  - [Server-Tabelle in lync Server 2013](lync-server-2013-servers-table.md)

  - [SessionDetails-Tabelle in lync Server 2013](lync-server-2013-sessiondetails-table.md)

  - [SIPResponseMetaData-Tabelle in lync Server 2013](lync-server-2013-sipresponsemetadata-table.md)

  - [Tabelle "Syndikator" in lync Server 2013](lync-server-2013-syndicators-table.md)

  - [SyndicatorsTenantMap-Tabelle in lync Server 2013](lync-server-2013-syndicatorstenantmap-table.md)

  - [Vorgangstabelle in lync Server 2013](lync-server-2013-task-table.md)

  - [Tabelle "Mandanten" in lync Server 2013](lync-server-2013-tenants-table.md)

  - [UriTypes-Tabelle in lync Server 2013](lync-server-2013-uritypes-table.md)

  - [Tabelle "Users" in lync Server 2013](lync-server-2013-users-table.md)

  - [UserAgentDef-Tabelle in lync Server 2013](lync-server-2013-useragentdef-table.md)

  - [UserStatistics-Tabelle in lync Server 2013](lync-server-2013-userstatistics-table.md)

  - [VoipDetails-Tabelle in lync Server 2013](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

