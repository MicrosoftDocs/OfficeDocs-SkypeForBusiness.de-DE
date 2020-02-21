---
title: Standard Migrationsszenario – High-Level
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5b2dd76a071c01c74f3d42f9c1ffbfa76c4a924
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a>Standard Migrationsszenario – High-Level

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-30_

Verwenden Sie die folgenden Elemente als Ausgangspunkt für die Migration lync Server 2010, Gruppenchats oder Office Communications Server 2007 R2 Gruppenchats zu lync Server 2013 persistent Chat Server. Der standardmäßige lync Server 2013 Migrationspfad lautet wie folgt:

  - Ihre Organisation hat zuvor lync Server 2010, Gruppenchat oder Office Communications Server 2007 R2 Gruppenchat bereitgestellt und Sie möchten lync Server 2013 Server für beständigen Chat bereitstellen.

  - Stellen Sie lync Server 2013 bereit, und stellen Sie dann den Server Pool für beständigen Chat bereit.

  - Vorbereiten und Planen der Migration Ihrer beständigen Chatrooms und bestimmen eines geeigneten Zeitraums zum Herunterfahren des Systems für die Migration.

  - Führen Sie die Windows PowerShell-Cmdlets für die Migration aus (**Export-CsPersistentChatData** und **Import-CsPersistentChatData**), um Inhalte auf den Server für beständigen Chat zu migrieren.

  - Stellen Sie sicher, dass die Migration erfolgreich war.

  - Außer Betrieb Ihrer Legacy-Bereitstellung.

  - Konfigurieren Sie den Server für beständigen Chat, damit ältere Clients eine Verbindung mit lync Server 2013, beständigen Chat Server herstellen können. Dies ist erforderlich, da die Bereitstellungneuer Clients Zeit in Anspruch nimmt und Sie möchten, dass vorhandene Benutzer mit älteren Clients so schnell wie möglich auf Ihre Chatrooms zugreifen können.

  - Stellen Sie neue Clients bereit, und stellen Sie sicher, dass Mitarbeiter mit Legacy Gruppenchat (Clients) in Ihre Chatrooms gelangen können.

</div>

<span> </span>

</div>

</div>

</div>

