---
title: 'Lync Server 2013: Definieren der Anforderungen für den Server für beständigen Chat'
description: 'Lync Server 2013: Definieren der Anforderungen für den Server für beständigen Chat.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af3fab1d91b78a5993f723b8fc6b375e4ab7cee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545351"
---
# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Definieren der Anforderungen Ihrer Organisation für den Server für beständigen Chat in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-01-15_

Bevor Sie den Server für beständigen Chat für Ihre Organisation bereitstellen, müssen Sie unbedingt die folgenden wichtigen Fragen zur Optimierung Ihrer Bereitstellung behandeln:

  - Wer (Benutzerprofil) sollte für den Server für beständigen Chat aktiviert werden? Der Server für beständigen Chat wird durch eine Richtlinie aktiviert, die auf globaler, Standort-, Pool-oder Benutzerebene festgelegt werden kann.

  - Wie viele Benutzer (Skalierung) sollten für den Server für beständigen Chat aktiviert werden? Der Server für beständigen Chat unterstützt 150.000-Benutzer (aktiviert nach Richtlinie) und maximal 80.000 gleichzeitige Benutzer mit persistent Chat Server. Ein einzelner Server für beständigen Chat kann 20.000 verbundene Benutzer unterstützen, und ein einzelner Serverpool für beständigen Chat kann bis zu 4 aktive Server für insgesamt 80.000 gleichzeitig verbundene Benutzer haben.

  - Migrieren Sie von einer früheren Version des Gruppen Chat Servers oder stellen Sie den Server für beständigen Chat zum ersten Mal bereit?

  - Gibt es Compliance-Anforderungen? Der Server für beständigen Chat unterstützt die Kompatibilität. Der Kompatibilitätsdienst wird auf dem Server für beständigen Chat Front-End-Server im Gegensatz zur Anforderung eines separaten Computers in früheren Gruppenchatserver-Bereitstellungen ausgeführt. Compliance ist optional und erfordert, falls ausgewählt, eine Kompatibilitätsdatenbank, die zum Speichern von Kompatibilitätsdaten und-Ereignissen konfiguriert werden muss. Möglicherweise möchten Sie auch einen Adapter konfigurieren, um die Daten aus der Kompatibilitätsdatenbank zu übernehmen und in ein anderes Format (beispielsweise XML-Dateien oder in Exchange gehostete Archive) zu konvertieren.

  - Wie sollen Bereiche, ethische Grenzen und Zugriffsmöglichkeiten kontrolliert werden? Mithilfe von **Kategorien** können Sie diese Grenzen ziehen und auswählen, welche Benutzer auf die Räume zugreifen können, die in den einzelnen Kategorien erstellt werden.

  - Wie soll kontrolliert werden, welche Benutzer Räume erstellen dürfen? Sie können unter Berücksichtigung Ihrer Kategorien **Ersteller** konfigurieren, die Räume erstellen dürfen. Ersteller können darüber hinaus andere Mitglieder für die laufende Verwaltung der Räume (Hinzufügen oder Entfernen von Mitgliedern) als **Chatroomanager** einsetzen. Die Grundlage hierfür ist der Bereich für **AllowedMembers/DeniedMembers**, der durch die jeweilige Kategorie festgelegt wird.

  - Wie möchten Sie Räume erstellen? Der Server für beständigen Chat stellt eine webbasierte Funktion zum Erstellen und Verwalten von Räumen bereit. Dies kann über den lync 2013-Client gestartet werden. Sie können eine benutzerdefinierte Lösung (mit dem Server Software Development Kit (SDK) für beständigen Chat) definieren, die Ihre geschäftlichen Anforderungen und Workflows implementiert, und den Server für beständigen Chat so konfigurieren, dass Benutzer zu Ihrer benutzerdefinierten Lösung geleitet werden.

  - Welche Arten von Add-Ins möchten Sie bereitstellen? **Add-ins** verbessern die in-Room-Erfahrung durch die Nutzung des Erweiterungsbereichs im lync 2013-Client, um für den raumrelevante Kontext bereitzustellen. Sie können die allgemeinen Add-Ins auswählen, die Ihnen (beispielsweise im Hinblick auf Ihre Unternehmenswebsite oder Dokumente für die interne Zusammenarbeit) am hilfreichsten erscheinen. Chatroom-Manager können bei Bedarf eines der registrierten Add-Ins auswählen und ihren Räumen zuordnen.

  - Welche Vorkehrungen wurden bezüglich der Anforderungen an die Hochverfügbarkeit sowie der Notfallwiederherstellung getroffen? Der Server für beständigen Chat unterstützt SQL Server Spiegelung und SQL Server Clustering für hohe Verfügbarkeit und unterstützt bis zu 8 Server (4 aktive und 4 Standby) in einem gestreckten Pool mit SQL Server Protokollversand für die Notfallwiederherstellung.

  - Gibt es regulatorische Anforderungen? Wenn sich Ihr Unternehmen in einem Land/einer Region befindet, in dem Daten innerhalb des Landes aufbewahrt werden müssen, müssen Sie möglicherweise mehrere Server Pools für beständigen Chat bereitstellen, die jeweils lokal in einer bestimmten geografischen Umgebung liegen. Ein Raum, eine Kategorie oder ein Add-in umfasst keine Pools – es gehört nur zu einem Server Pool für beständigen Chat. Sie können die Gruppe von Kategorien, Add-Ins und Chatrooms für jeden Server Pool für beständigen Chat verwalten. Benutzer können so konfiguriert werden, dass Sie den Zugriff auf Chatrooms in einem oder mehreren Pools mithilfe des Bereichs oder der Mitgliedschafts Bereiche der Kategorie AllowedMembers, je nachdem, wie Sie Ihre Kategorien entwerfen.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie über mehrere Server Pools für beständigen Chat verfügen, erhalten Sie keinen größeren Maßstab (Sie können weiterhin nur 80.000 gleichzeitig verbundene Benutzer über alle Ihre Server Pools für beständigen Chat verfügen). Der Hauptgrund für die Unterstützung mehrerer Server Pools für beständigen Chat besteht darin, regulatorische Belange zu unterstützen.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

