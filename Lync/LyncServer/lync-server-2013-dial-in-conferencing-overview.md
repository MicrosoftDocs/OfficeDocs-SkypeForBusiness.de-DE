---
title: Übersicht über lync Server 2013 Einwahlkonferenzen
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
ms.openlocfilehash: d91c455c1e4bfbb2b4fe7af827265a789c9ace68
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498932"
---
# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a>Übersicht über Einwahlkonferenzen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-30_

Wenn Ihre Organisation über Benutzer verfügt, die lync Server 2013 lokalen Konferenzen teilnehmen müssen, wenn Sie nicht im Büro sind oder keinen Zugriff auf einen Computer haben, können Sie Einwahlkonferenzen bereitstellen, damit Sie über ein PSTN-Telefon (Public Switched Telephone Network) an der Konferenz teilnehmen können.

Einwahlkonferenzen sind ein optionales Feature, das Sie bei der Bereitstellung von lync Server 2013 Konferenzen konfigurieren können. Bei Einwahlkonferenzen werden zwar einige der lync Server 2013 Komponenten verwendet, die Enterprise-VoIP verwendet, aber Sie können Einwahlkonferenzen auch dann bereitstellen, wenn Sie Enterprise-VoIP nicht bereitstellen.

<div>


> [!NOTE]  
> Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie Sie in jedem Pool bereitstellen, in dem Sie lync Server 2013 Konferenzen bereitstellen. Sie müssen nicht in jedem Pool Zugriffsnummern zuweisen, aber Sie müssen die Einwahlfunktion in jedem Pool bereitstellen. Diese Anforderung unterstützt das Feature für aufgezeichnete Namen, wenn ein Benutzer eine Zugriffsnummer aus einem Pool aufruft, um an einer lync Server 2013 Konferenz in einem anderen Pool teilzunehmen.



</div>

Konferenzen müssen in der Besprechungsrichtlinie für den Zugriff per Einwahl aktiviert werden. In der Standardeinstellung umfassen Konferenzen, die für den Zugriff per Einwahl aktiviert sind, die folgenden Informationen in der Konferenzeinladung:

  - Eine numerische Konferenz-ID, die zur Identifizierung der Konferenz dient.

  - Mindestens eine PSTN-Zugriffsnummer.

  - Ein Link zu einer Seite "Einstellungen für Einwahlkonferenzen", die eine vollständige Liste der Zugriffsnummern mit ihren zugeordneten Sprachen enthält; ein Ort zum Erstellen, zurücksetzen oder Aufheben der Blockierung persönlicher Identifikationsnummern (Pins); und andere Informationen, wie etwa DTMF-Steuerelemente (Dual-Tone Multi-Frequency).

Einwahlkonferenzen können sowohl für Unternehmensbenutzer als auch für anonyme Benutzer eingesetzt werden. Enterprise-Benutzer verfügen über Active Directory-Domänendienste Anmeldeinformationen und lync Server 2013 Konten in Ihrer Organisation. Anonyme Benutzer verfügen nicht über Anmeldeinformationen innerhalb Ihrer Organisation. Im Zusammenhang mit Einwahlkonferenzen wird ein Benutzer in einer Organisation eines Verbundpartners, der über PSTN eine Verbindung mit einer Konferenz herstellt, als anonymer Benutzer betrachtet. Im Gegensatz zu anderen Kontexten werden Partnerbenutzer bei Einwahlkonferenzen nicht authentifiziert.

Unternehmensbenutzer oder Konferenzleiter, die einer für den Zugriff per Einwahl aktivierten Konferenz beitreten, wählen eine der Zugriffsnummern für die Konferenz und werden anschließend zur Eingabe der Konferenz-ID aufgefordert. Wenn der Konferenzleiter der Besprechung noch nicht beigetreten ist, können Benutzer entweder ihre Unified Communications-Durchwahl (UC) (oder die vollständige Telefonnummer) und PIN eingeben oder warten, bis der Konferenzleiter bestätigt, dass sie zur Konferenz zugelassen werden. Besprechungsorganisatoren können der Besprechung als Konferenzleiter beitreten, indem sie lediglich ihre PIN eingeben. In der Front-End-Server wird die Kombination aus vollständiger Telefonnummer oder Durchwahl und PIN verwendet, um Enterprise-Benutzer eindeutig ihren Active Directory Anmeldeinformationen zuzuordnen. So werden Unternehmensbenutzer anhand ihres Namens in der Konferenz authentifiziert und identifiziert. Unternehmensbenutzer können auch eine Konferenzrolle übernehmen, die vom Organisator vorgegeben ist.

<div>


> [!NOTE]  
> Unternehmensbenutzer, die sich über ein Office-IP-Telefon oder über lync Server 2013 oder lync 2010 Attendant einwählen, werden nicht zur Eingabe Ihrer Telefonnummer aufgefordert, da Sie bereits authentifiziert sind.



</div>

Anonyme Benutzer, die einer Einwahlkonferenz beitreten möchten, wählen eine der Zugriffsnummern für die Konferenz und werden zur Eingabe der Konferenz-ID aufgefordert. Nicht authentifizierte anonyme Benutzer werden zudem zur Aufzeichnung ihres Namens aufgefordert. Der aufgezeichnete Name identifiziert nicht authentifizierte Benutzer in der Konferenz. Anonyme Benutzer werden erst zur Konferenz zugelassen, wenn mindestens ein Konferenzleiter oder authentifizierter Benutzer beigetreten ist. Das Zuweisen einer vordefinierten Rolle zu anonymen Benutzern ist nicht möglich.

<div>


> [!NOTE]  
> Unternehmensbenutzer, die ihre Telefonnummer und PIN nicht eingeben, werden nicht authentifiziert. Diese Benutzer werden zur Aufzeichnung ihres Namens aufgefordert und in der Konferenz als anonyme Benutzer behandelt.



</div>

Zu einem geplanten Zeitpunkt kann der Besprechungsorganisator den Zugriff auf die Besprechung einschränken, indem er die Besprechung als geschlossen oder gesperrt kennzeichnet. In diesem Fall müssen sich Einwahlbenutzer authentifizieren. Wenn Einwahlbenutzer nicht authentifiziert werden können oder keine Authentifizierung durchführen möchten, werden sie in die Lobby umgeleitet. Sie warten in der Lobby, bis der Besprechungsleiter ihre Teilnahme bestätigt oder ablehnt oder die Verbindung aufgrund einer Zeitüberschreitung getrennt wird. Während der Wartezeit wird für Einwahlbenutzer Musik wiedergegeben. Nachdem Einwahlbenutzer zu einer Konferenz zugelassen wurden, können sie am Audioteil der Konferenz teilnehmen und DTMF-Befehle (Dual-Tone Multi-Frequency, Mehrfrequenzverfahren) über die Telefontastatur ausführen. Besprechungsleiter von Einwahlkonferenzen nutzen DTMF-Befehle zum Steuern, ob sich Teilnehmer selbst stumm schalten können oder nicht, zum Sperren oder Aufheben der Sperrung einer Konferenz, zum Zulassen von Teilnehmern aus der Lobby und zum Ein- und Ausschalten von Ansagen beim Beitreten und Verlassen. Konferenzleiter können mithilfe von DTMF-Befehlen zudem alle Teilnehmer aus der Lobby zulassen. Durch diese Aktion werden die Berechtigungen für die Besprechung so geändert, dass anschließend sämtliche Benutzer zugelassen werden, die der Besprechung beitreten. Alle eingewählten Teilnehmer können DTMF-Befehle ausführen, um Hilfeinformationen abzuhören, die Namen der Teilnehmer wiederzugeben und sich selbst stumm zu schalten.

Für eingewählte Teilnehmer werden unabhängig davon, ob sie sich über das Festnetz einwählen oder nicht, während der Konferenz persönliche Ansagen wiedergegeben. Diese Informationen umfassen z. B., ob die Teilnehmer stumm geschaltet wurden oder nicht, ob die Besprechung aufgezeichnet wird oder ob Benutzer in der Lobby warten.

<div>


> [!NOTE]  
> Für Teilnehmer, die sich nicht einwählen, sondern der Besprechung über einen Link beitreten, werden keine persönlichen Ansagen wiedergegeben.



</div>

</div>

<span> </span>

</div>

</div>

</div>

