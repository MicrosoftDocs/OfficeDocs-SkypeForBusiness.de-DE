---
title: 'Lync Server 2013: Definieren der Anforderungen Ihrer Organisation an den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68f9195a91a4f8334933d1fce7ffd3a5dceb564c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Definieren der Anforderungen Ihrer Organisation an den Server für beständigen Chat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-01-15_

Bevor Sie den beständigen Chat Server für Ihre Organisation bereitstellen, müssen Sie unbedingt die folgenden wichtigen Fragen zur Optimierung Ihrer Bereitstellung in Frage stellen:

  - Wer (Benutzerprofil) sollte für beständigen Chat Server aktiviert sein? Der Server für beständigen Chat wird durch eine Richtlinie aktiviert, die auf globaler, Website-, Pool-oder Benutzerebene festgesetzt werden kann.

  - Wie viele Benutzer (Skalierung) sollten für beständigen Chat Server aktiviert sein? Der beständige Chat Server unterstützt 150.000 bereitgestellte Benutzer (aktiviert durch Richtlinie) und maximal 80.000 gleichzeitige Benutzer, die den beständigen Chat Server verwenden. Ein einzelner Server für beständigen Chat kann 20.000 verbundene Benutzer unterstützen und ein Serverpool für beständigen Chat kann bis zu 4 aktive Server für insgesamt 80.000 gleichzeitig verbundene Benutzer bedienen.

  - Migrieren Sie von einer früheren Version des Gruppen-Chat Servers, oder stellen Sie zum ersten Mal einen beständigen Chat Server bereit?

  - Gibt es Compliance-Anforderungen? Der beständige Chat Server unterstützt Compliance. Der Kompatibilitätsdienst wird auf dem Front-End-Server für beständigen Chat Server ausgeführt, im Gegensatz zur Anforderung für einen separaten Computer in vorherigen Gruppen Chat Server Bereitstellungen. Compliance ist optional und erfordert bei Auswahl eine Kompatibilitätsdatenbank, die zum Speichern von Kompatibilitätsdaten und Ereignissen konfiguriert werden muss. Möglicherweise möchten Sie auch einen Adapter konfigurieren, um die Daten aus der Kompatibilitätsdatenbank zu übernehmen und in ein anderes Format (wie XML-Dateien oder Exchange-gehostete Archive) zu konvertieren.

  - Wie sollen Bereiche, ethische Grenzen und Zugriffsmöglichkeiten kontrolliert werden? Sie können **Kategorien** definieren, um diese Grenzen zu trennen, und auswählen, wer in Räumen sein darf, die in jeder dieser Kategorien erstellt werden.

  - Wie soll kontrolliert werden, wer Räume erstellen kann? Sie können für **** Ihre Kategorien geeignete Creators konfigurieren, die Räume erstellen können. Autoren können anderen Mitgliedern als Chatroom- **Manager** für die laufende Verwaltung der Räume (hinzufügen oder Entfernen zusätzlicher Mitglieder) entsprechend dem von der Kategorie konfigurierten Bereich für **AllowedMembers/DeniedMembers** zuweisen.

  - Wie möchten Sie Räume erstellen? Der Server für beständigen Chat bietet ein webbasiertes Feature für die Erstellung und Verwaltung von Räumen. Dies kann über den lync 2013-Client gestartet werden. Sie können eine benutzerdefinierte Lösung (mit dem Server Software Development Kit (SDK) für beständigen Chat) definieren, die Ihre geschäftlichen Anforderungen und Workflows implementiert, und den beständigen Chat Server so konfigurieren, dass Benutzer an Ihre benutzerdefinierte Lösung weitergeleitet werden.

  - Welche Arten von Add-Ins möchten Sie bereitstellen? **Add-ins** verbessern die in-Room-Umgebung, indem Sie den Bereich "Erweiterbarkeit" im lync 2013-Client nutzen, um Kontext bereitzustellen, der für den Raum relevant ist. Sie können die allgemeinen Add-Ins auswählen, die Ihnen (beispielsweise im Hinblick auf Ihre Unternehmenswebsite oder Dokumente für die interne Zusammenarbeit) am hilfreichsten erscheinen. Chatroom-Manager können bei Bedarf eines der registrierten Add-Ins auswählen und ihren Räumen zuordnen.

  - Welche Vorkehrungen wurden bezüglich der Anforderungen an hohe Verfügbarkeit sowie der Notfallwiederherstellung getroffen? Der beständige Chat Server unterstützt die SQL Server-Spiegelung und das SQL Server-Clustering für höchste Verfügbarkeit und unterstützt bis zu 8 Server (4 Active und 4 Standby) in einem gedehnten Pool mit SQL Server-Protokollversand für Disaster Recovery.

  - Bestehen gesetzliche Vorschriften? Wenn sich Ihr Unternehmen in einem Land/einer Region befindet, in dem Daten im Land aufbewahrt werden müssen, müssen Sie möglicherweise mehrere beständige Chat Server Pools bereitstellen, die jeweils lokal in einer bestimmten geografischen Umgebung gespeichert sind. Ein Raum, eine Kategorie oder ein Add-in umfasst keine Pools, sondern gehört nur zu einem beständigen Chat Server Pool. Sie können die Gruppe von Kategorien, Add-Ins und Räumen für jeden beständigen Chat Server Pool verwalten. Je nachdem, wie Sie Ihre Kategorien entwerfen, können Benutzer so konfiguriert werden, dass Sie den Zugriff auf Räume in einem oder mehreren Pools unter Verwendung des Bereichs "Kategorie AllowedMembers" oder des Mitgliedschafts Bereichs des Raums haben.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie über mehrere Server Pools für beständigen Chat verfügen, können Sie nicht mehr skalieren (Sie können immer noch nur 80.000-gleichzeitig verbundene Benutzer über alle Ihre beständigen Chat Server Pools verfügen). Der Hauptgrund für die Unterstützung mehrerer beständiger Chat Server Pools ist die Unterstützung behördlicher Bedenken.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

