---
title: 'Lync Server 2013: Voraussetzungen für die Aktivierung der Kerberos-Authentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5fa366ae27126ead478d66c3beb091581158d1a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>Voraussetzungen für die Aktivierung der Kerberos-Authentifizierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Stellen Sie vor dem Aktivieren der Kerberos-Authentifizierung sicher, dass Sie alle erforderlichen Konfigurations-und Infrastruktur Vorbereitungen ausführen:

  - Active Directory Schema wird für lync Server 2013 erweitert.

  - Active Directory Gesamtstrukturvorbereitung ist für lync Server 2013 abgeschlossen.

  - Active Directory Domänenvorbereitung ist für lync Server 2013 abgeschlossen.

  - Der zentrale Verwaltungsspeicher wurde erfolgreich installiert und ist verfügbar.

  - Die Topologie wurde mithilfe des Topologie-Generators erstellt und veröffentlicht.

  - Server und Rollen, die Webdienste erfordern, wurden definiert und bereitgestellt, einschließlich Front-End-Server, Standard Edition-Server und Directors.

  - Internet Information Services (IIS) wird mit den empfohlenen Rollendiensten konfiguriert und bereitgestellt, um Webdienste in lync Server 2013 zu unterstützen.

Nachdem die Voraussetzungen erfüllt sind, sollten Sie bereit sein, ein oder mehrere Konten für Webdienste zu erstellen, die für die Kerberos-Authentifizierung für Ihre Bereitstellung verwendet werden sollen. Sie müssen pro Bereitstellung mindestens ein Kerberos-Authentifizierungskonto erstellen. Sie können jedoch ein Konto für jeden Standort erstellen, um eine lokale Kerberos-Authentifizierung am Standort zu ermöglichen. Pro Standort kann nur ein Kerberos-Authentifizierungskonto angegeben werden.

</div>

<span> </span>

</div>

</div>

</div>

