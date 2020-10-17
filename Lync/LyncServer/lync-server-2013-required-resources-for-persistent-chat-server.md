---
title: 'Lync Server 2013: erforderliche Ressourcen für den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156a3ffef41782760124f0eb791cf2fdb71a1235
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511942"
---
# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a>Erforderliche Ressourcen für den Server für beständigen Chat in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-02-05_

Hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat erfordern zusätzliche Ressourcen, die in der Regel für den vollständigen Betrieb erforderlich sind. Stellen Sie vor dem Konfigurieren des Servers für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung sicher, dass Sie über die folgenden Ressourcen verfügen, zusätzlich zu den Anforderungen für den Servervorgang für den standardmäßigen beständigen Chat. Weitere Konfigurationsinformationen finden Sie unter [Configuring persistent Chat Server in lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).

  - Eine dedizierte Datenbankinstanz, die sich im selben physischen Rechenzentrum befindet, in dem sich das Hauptfront-End des Server Diensts für beständigen Chat befindet. Diese Datenbank wird als SQL Server Spiegel für die primäre Datenbank für beständigen Chat fungieren. Legen Sie optional eine zusätzliche SQL Server fest, die als Spiegelungs Zeuge fungieren soll, wenn Sie ein automatisches Failover für die Spiegeldatenbank wünschen.

  - Eine dedizierte Datenbankinstanz im anderen physischen Rechenzentrum. Diese Datenbank dient als SQL Server Protokollversand sekundäre Datenbank für die Datenbank im primären Rechenzentrum.

  - Eine dedizierte Datenbankinstanz, die als SQL Server Spiegel für die sekundäre Datenbank dient. Optional können Sie einen zusätzlichen SQL Server als Spiegelungs Zeugen für Server festlegen. Beide Instanzen müssen sich im selben physischen Rechenzentrum wie die sekundäre Datenbank befinden.

  - Wenn die Kompatibilität für den beständigen Chat Server aktiviert ist, sind weitere drei dedizierte Datenbankinstanzen erforderlich. Die Verteilung entspricht denen, die zuvor für die Datenbank für beständigen Chat beschrieben wurden. Es ist zwar möglich, dass die Kompatibilitätsdatenbank dieselbe SQL Server Instanz wie die Datenbank für beständigen Chat hat, es wird jedoch empfohlen, eigenständige Instanzen für hohe Verfügbarkeit und Notfallwiederherstellung zu verwenden.

  - Eine Dateifreigabe muss für die SQL Server Protokollversand-Transaktionsprotokolle erstellt und festgelegt werden. Alle SQL-Server in beiden Rechenzentren, auf denen persistente Chat Datenbanken ausgeführt werden, müssen über Lese-/Schreibzugriff auf diese Dateifreigabe verfügen. Diese Freigabe ist nicht als Teil einer Filestore-Rolle definiert.

  - Eine Dateifreigabe auf dem sekundären Datenbankserver, die als Zielordner für die SQL Server Transaktionsprotokolle dient, die von der Dateifreigabe des primären Servers kopiert werden.

<div>


> [!NOTE]  
> Aktive persistent Chat-Server in einem Serverpool für beständigen Chat müssen sich in derselben Zeitzone befinden wie der lync-Pool für den nächsten Hop, der in der Topologie definiert ist.



</div>

Die folgenden Abbildungen bieten Beispiele dafür, wie der gesamte Server Pool für beständigen Chat in den beiden unterschiedlichen Topologien mit gestreckten Pools konfiguriert werden kann:

  - Erweiterter Pool mit Servern für beständigten Chat, bei dem die Geolocation der Rechenzentren eine hohe Bandbreite bzw. eine geringe Wartezeit aufweist.

  - Erweiterter Pool mit Servern für beständigen Chat, bei dem die Geolocation der Rechenzentren eine geringe Bandbreite bzw. eine lange Wartezeit aufweist.

In der folgenden Abbildung ist eine gestreckte Server Pooltopologie mit beständigem Chat dargestellt, in der sich Rechenzentren mit hoher Bandbreite und niedriger Latenz geografischer Standorte befinden.

**Erweiterter Pool mit Servern für beständigten Chat, bei dem die Geolocation der Rechenzentren eine hohe Bandbreite bzw. eine geringe Wartezeit aufweist.**

![Server Pool für beständigen Chat HBW-Konfigurationsprüfung](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Server Pool für beständigen Chat HBW-Konfigurationsprüfung")

In der folgenden Abbildung ist eine gestreckte Server Pooltopologie mit beständigem Chat dargestellt, in der sich Rechenzentren mit geringer Bandbreite und hoher Latenz befinden.

**Erweiterter Pool mit Servern für beständigen Chat, bei dem die Geolocation der Rechenzentren eine geringe Bandbreite bzw. eine lange Wartezeit aufweist.**

![Server Pool für beständigen Chat LBW-Konfigurationsprüfung](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Server Pool für beständigen Chat LBW-Konfigurationsprüfung")

</div>

<span> </span>

</div>

</div>

</div>

