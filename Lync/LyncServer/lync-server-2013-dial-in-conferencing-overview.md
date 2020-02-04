---
title: Übersicht über Einwahlkonferenzen in lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a126e7e1ee61f48ff8857553b7677abf813a25e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a>Übersicht über Einwahlkonferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-30_

Wenn in Ihrer Organisation Benutzer vorhanden sind, die an den lokalen Konferenzen von lync Server 2013 teilnehmen müssen, wenn Sie nicht im Büro sind oder keinen Zugriff auf einen Computer haben, können Sie Einwahlkonferenzen bereitstellen, damit Sie mit einem öffentlich geschalteten Telefon an der Konferenz teilnehmen können. Netz Telefon (PSTN).

Einwahlkonferenzen sind ein optionales Feature, das Sie beim Bereitstellen von lync Server 2013-Konferenzen konfigurieren können. Obwohl Einwahlkonferenzen einige der gleichen lync Server 2013-Komponenten verwenden, die Enterprise-VoIP verwendet, können Sie Einwahlkonferenzen auch dann bereitstellen, wenn Sie Enterprise-VoIP nicht bereitstellen.

<div>


> [!NOTE]  
> Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie Sie in jedem Pool bereitstellen, in dem Sie die lync Server 2013-Konferenz bereitstellen. Sie müssen keine Zugriffsnummern in jedem Pool zuweisen, aber Sie müssen das Einwahlfeature in jedem Pool bereitstellen. Diese Anforderung unterstützt das Feature "aufgezeichnete Namen", wenn ein Benutzer eine Zugriffsnummer aus einem Pool anruft, um an einer lync Server 2013-Konferenz in einem anderen Pool teilzunehmen.



</div>

Konferenzen müssen für Einwahlzugriff in Besprechungsrichtlinien aktiviert sein. In der Standardeinstellung umfassen Konferenzen, die für den Zugriff per Einwahl aktiviert sind, die folgenden Informationen in der Konferenzeinladung:

  - Eine numerische Konferenz-ID, die die Konferenz kennzeichnet.

  - Eine oder mehrere PSTN-Zugriffsnummern.

  - Einen Link zu einer Seite mit Einstellungen für Einwahlkonferenzen, die eine vollständige Liste der Zugriffsnummern mit den zugehörigen Sprachen enthält; ein Ort zum Erstellen, zurücksetzen oder entsperren persönlicher Identifikationsnummern (Pins); und weitere Informationen, wie etwa DTMF-Steuerelemente (Dual Tone Multi-Frequency).

Einwahlkonferenzen können sowohl für Unternehmensbenutzer als auch für anonyme Benutzer eingesetzt werden. Unternehmensbenutzer verfügen über die Anmeldeinformationen für Active Directory-Domänendienste und lync Server 2013-Konten innerhalb Ihrer Organisation. Anonyme Benutzer verfügen über keine Anmeldeinformationen innerhalb Ihrer Organisation. Im Zusammenhang mit Einwahlkonferenzen wird ein Benutzer in einer Organisation eines Verbundpartners, der über PSTN eine Verbindung mit einer Konferenz herstellt, als anonymer Benutzer betrachtet. Im Gegensatz zu anderen Kontexten werden Partnerbenutzer bei Einwahlkonferenzen nicht authentifiziert.

Unternehmensbenutzer oder Konferenzleiter, die einer für den Zugriff per Einwahl aktivierten Konferenz beitreten, wählen eine der Zugriffsnummern für die Konferenz und werden anschließend zur Eingabe der Konferenz-ID aufgefordert. Wenn der Konferenzleiter der Besprechung noch nicht beigetreten ist, können Benutzer entweder ihre Unified Communications-Durchwahl (UC) (oder die vollständige Telefonnummer) und PIN eingeben oder warten, bis der Konferenzleiter bestätigt, dass sie zur Konferenz zugelassen werden. Besprechungsorganisatoren können der Besprechung als Konferenzleiter beitreten, indem sie lediglich ihre PIN eingeben. Der Front-End-Server verwendet die Kombination aus der vollständigen Telefonnummer oder Durchwahl und der PIN, um Unternehmensbenutzer eindeutig ihren Active-Anmeldeinformationen zuzuordnen. So werden Unternehmensbenutzer anhand ihres Namens in der Konferenz authentifiziert und identifiziert. Unternehmensbenutzer können auch eine Konferenzrolle übernehmen, die vom Organisator vorgegeben ist.

<div>


> [!NOTE]  
> Enterprise-Benutzer, die sich über ein Office-IP-Telefon oder über lync Server 2013 oder lync 2010 Attendant einwählen, werden nicht zur Eingabe Ihrer Telefonnummer aufgefordert, da Sie bereits authentifiziert sind.



</div>

Anonyme Benutzer, die einer Einwahlkonferenz beitreten möchten, wählen eine der Zugriffsnummern für die Konferenz und werden zur Eingabe der Konferenz-ID aufgefordert. Nicht authentifizierte anonyme Benutzer werden zudem zur Aufzeichnung ihres Namens aufgefordert. Der aufgezeichnete Name identifiziert nicht authentifizierte Benutzer in der Konferenz. Anonyme Benutzer werden erst zur Konferenz zugelassen, wenn mindestens ein Konferenzleiter oder authentifizierter Benutzer beigetreten ist. Das Zuweisen einer vordefinierten Rolle zu anonymen Benutzern ist nicht möglich.

<div>


> [!NOTE]  
> Unternehmensbenutzer, die ihre Telefonnummer und PIN nicht eingeben, werden nicht authentifiziert. Diese Benutzer werden zur Aufzeichnung ihres Namens aufgefordert und in der Konferenz als anonyme Benutzer behandelt.



</div>

Zur Zeitplanung kann der Besprechungsorganisator den Zugriff auf die Besprechung einschränken, indem die Besprechung geschlossen oder gesperrt wird. In diesem Fall müssen sich die Benutzer bei der Einwahl authentifizieren. Wenn Benutzer von Einwahl Fehlern Versagen oder sich nicht authentifizieren möchten, werden Sie in die Lobby übertragen. Sie warten in der Wartehalle, bis eine Führungslinie Sie annimmt oder ablehnt, oder Sie verfallen und werden getrennt. Einwahlbenutzer hören Musik, wenn Sie darauf warten, zur Konferenz zugelassen zu werden. Sobald Einwahlbenutzer zu einer Konferenz zugelassen wurden, können sie am Audioteil der Konferenz teilnehmen und über das Tastenfeld ihres Telefons DTMF-Befehle (Dual-Tone Multi-Frequency, Mehrfrequenzverfahren) eingeben. Der Leiter einer Einwahlkonferenz kann mithilfe von DTMF-Befehlen die Möglichkeit der Teilnehmer zur Stummschaltung ein- oder ausschalten, die Konferenz sperren oder entsperren, Personen aus der Lobby aufnehmen sowie Ankündigungen bei Zu- und Abgang ein- bzw. ausschalten. Konferenzleiter können mithilfe von DTMF-Befehlen zudem alle Teilnehmer aus der Lobby zulassen. Durch diese Aktion werden die Berechtigungen für die Besprechung so geändert, dass anschließend sämtliche Benutzer zugelassen werden, die der Besprechung beitreten. Alle eingewählten Teilnehmer können DTMF-Befehle ausführen, um Hilfeinformationen abzuhören, die Namen der Teilnehmer wiederzugeben und sich selbst stumm zu schalten.

Einwahl Teilnehmer (das heißt, ob Sie aus dem PSTN wählen), während der Konferenz persönliche Ankündigungen hören, beispielsweise ob Sie stumm geschaltet oder nicht stumm geschaltet wurden, die Besprechung aufgezeichnet wird oder jemand in der Lobby wartet.

<div>


> [!NOTE]  
> Für Teilnehmer, die sich nicht einwählen, sondern der Besprechung über einen Link beitreten, werden keine persönlichen Ansagen wiedergegeben.



</div>

</div>

<span> </span>

</div>

</div>

</div>

