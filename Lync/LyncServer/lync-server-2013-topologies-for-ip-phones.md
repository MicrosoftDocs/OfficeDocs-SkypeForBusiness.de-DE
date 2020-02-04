---
title: 'Lync Server 2013: Topologien für IP-Telefone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e05a56d30167f2e20a383cde9fcfaaa70418e650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a>Topologien für IP-Telefone in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-21_

Dieser Abschnitt bietet einen Überblick über den Verbindungsprozess und erläutert die Unterschiede zwischen der Verbindung eines IP-Telefons in einem internen und einem externen Netzwerk.

<div>


> [!NOTE]  
> Lync Server bietet Unterstützung für die folgenden IP-Telefone: das Aastra 6721ip-Telefon, das Aastra 6725ip-Telefon, das HP 4110-IP-Telefon (Common Area Phone), das HP 4120 IP-Telefon (Tischtelefon), das Polycom CX600 IP-Tischtelefon, das Polycom CX700-IP-Tischtelefon, Polycom CX500 IP Telefon mit gemeinsamem Bereich und Polycom CX3000 IP-Konferenztelefon. Von diesen Telefonen kann nur die Polycom CX700 lync Phone Edition ausführen.



</div>

Das folgende Diagramm beschreibt alle Komponenten, die für die Gerätekonnektivität innerhalb der Unternehmensumgebung erforderlich sind.

**Interne Topologie**

![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")

<div>


> [!NOTE]  
> Bei der vorherigen Abbildung handelt es sich um eine logische Darstellung, keine physische Übersicht. Beispielsweise befindet sich die Active Directory-Domänendienste (AD DS) selten auf demselben Computer wie alle lync Server-Komponenten. Der Benutzerspeicher kann sich auf dem Back-End-Server oder auf den Archivierungs-und Überwachungs Servern befinden. Die lync Server-Verwaltungsshell, Webserver und Updatedienste sind Teil der Front-End-Serverrolle.



</div>

Das folgende Diagramm bietet eine Übersicht über die beteiligten Komponenten, wenn sich das Gerät außerhalb des Unternehmensnetzwerks befindet.

**Externe Topologie**

![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")

<div>


> [!NOTE]  
> Der Geräte Update-Webdienst bietet eine externe und interne Website, aber nur die externe Website wird hier angezeigt.<BR>Der Speicherort der Registrierungsstelle und die URL des Geräte Update-Webdiensts für die Organisation müssen in DNS veröffentlicht werden, wenn externer Zugriff aktiviert werden soll. Darüber hinaus muss der Edgeserver bereitgestellt und ordnungsgemäß konfiguriert werden, um die externe Kommunikation vom Gerät zur Unternehmensumgebung und zurück zu ermöglichen. Dies wird im vorherigen Diagramm ausgelassen, da die Edge-Bereitstellung nicht für die Gerätekonnektivität spezifisch ist.



</div>

</div>

<span> </span>

</div>

</div>

</div>

