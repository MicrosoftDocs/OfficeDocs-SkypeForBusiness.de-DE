---
title: Übersicht über Einwahlkonferenzen
TOCTitle: Übersicht über Einwahlkonferenzen
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398524(v=OCS.15)
ms:contentKeyID: 49294342
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über Einwahlkonferenzen

 

_**Letztes Änderungsdatum des Themas:** 2012-09-30_

Wenn Ihre Organisation über Benutzer verfügt, die an lokalen Lync Server 2013-Konferenzen teilnehmen müssen, wenn sie sich nicht im Büro befinden oder keinen Zugriff auf einen Computer haben, können Sie die Funktion für Einwahlkonferenzen bereitstellen, sodass diese Benutzer über ein Festnetztelefon an der Konferenz teilnehmen können.

Einwahlkonferenzen sind eine optionale Funktion bei der Bereitstellung von Lync Server 2013-Konferenzen. Wenngleich Einwahlkonferenzen einige Lync Server 2013-Komponenten verwenden, die auch von Enterprise-VoIP verwendet werden, ist die Bereitstellung von Enterprise-VoIP nicht erforderlich, um Einwahlkonferenzen bereitzustellen.


> [!NOTE]
> Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie diese Funktion in jedem Pool bereitstellen, in dem Lync Server 2013-Konferenzen bereitgestellt werden. Sie müssen nicht in jedem Pool Zugriffsnummern zuweisen, aber Sie müssen die Einwahlfunktion in jedem Pool bereitstellen. Diese Anforderung muss für die Funktion für aufgezeichnete Namen erfüllt werden, wenn ein Benutzer eine Zugriffsnummer aus einem Pool wählt, um an einer Lync Server 2013-Konferenz in einem anderen Pool teilzunehmen.



Konferenzen müssen in der Besprechungsrichtlinie für den Zugriff per Einwahl aktiviert werden. In der Standardeinstellung umfassen Konferenzen, die für den Zugriff per Einwahl aktiviert sind, die folgenden Informationen in der Konferenzeinladung:

  - Eine numerische Konferenz-ID, die zur Identifizierung der Konferenz dient.

  - Mindestens eine PSTN-Zugriffsnummer.

  - Einen Link zur Seite "Einstellungen für Einwahlkonferenz", die eine vollständige Liste der Zugriffsnummern mit den zugehörigen Sprachen enthält; eine Möglichkeit zum Erstellen, Zurücksetzen und Aufheben der Sperrung von PINs (Personal Identification Number) sowie andere Informationen wie z. B. DTMF-Steuerelemente (Dual-Tone Multi-Frequency, Mehrfrequenzverfahren).

Einwahlkonferenzen können sowohl für Unternehmensbenutzer als auch für anonyme Benutzer eingesetzt werden. Unternehmensbenutzer verfügen über Anmeldeinformationen für die Active Directory-Domänendienste und ein Lync Server 2013-Konto innerhalb ihrer Organisation. Anonyme Benutzer verfügen nicht über Anmeldeinformationen innerhalb Ihrer Organisation. Im Zusammenhang mit Einwahlkonferenzen wird ein Benutzer in einer Organisation eines Verbundpartners, der über PSTN eine Verbindung mit einer Konferenz herstellt, als anonymer Benutzer betrachtet. Im Gegensatz zu anderen Kontexten werden Partnerbenutzer bei Einwahlkonferenzen nicht authentifiziert.

Unternehmensbenutzer oder Konferenzleiter, die einer für den Zugriff per Einwahl aktivierten Konferenz beitreten, wählen eine der Zugriffsnummern für die Konferenz und werden anschließend zur Eingabe der Konferenz-ID aufgefordert. Wenn der Konferenzleiter der Besprechung noch nicht beigetreten ist, können Benutzer entweder ihre Unified Communications-Durchwahl (UC) (oder die vollständige Telefonnummer) und PIN eingeben oder warten, bis der Konferenzleiter bestätigt, dass sie zur Konferenz zugelassen werden. Besprechungsorganisatoren können der Besprechung als Konferenzleiter beitreten, indem sie lediglich ihre PIN eingeben. Der Front-End-Server verwendet die Kombination aus der vollständigen Telefonnummer oder Durchwahl und der PIN, um Unternehmensbenutzer eindeutig ihren Active Directory-Anmeldeinformationen zuzuordnen. So werden Unternehmensbenutzer anhand ihres Namens in der Konferenz authentifiziert und identifiziert. Unternehmensbenutzer können auch eine Konferenzrolle übernehmen, die vom Organisator vorgegeben ist.


> [!NOTE]
> Unternehmensbenutzer, die sich über ein IP-Bürotelefon oder über Lync Server 2013 oder Lync 2010-Vermittlung einwählen, werden nicht zur Eingabe ihrer Telefonnummer aufgefordert, da sie bereits authentifiziert sind.



Anonyme Benutzer, die einer Einwahlkonferenz beitreten möchten, wählen eine der Zugriffsnummern für die Konferenz und werden zur Eingabe der Konferenz-ID aufgefordert. Nicht authentifizierte anonyme Benutzer werden zudem zur Aufzeichnung ihres Namens aufgefordert. Der aufgezeichnete Name identifiziert nicht authentifizierte Benutzer in der Konferenz. Anonyme Benutzer werden erst zur Konferenz zugelassen, wenn mindestens ein Konferenzleiter oder authentifizierter Benutzer beigetreten ist. Das Zuweisen einer vordefinierten Rolle zu anonymen Benutzern ist nicht möglich.


> [!NOTE]
> Unternehmensbenutzer, die ihre Telefonnummer und PIN nicht eingeben, werden nicht authentifiziert. Diese Benutzer werden zur Aufzeichnung ihres Namens aufgefordert und in der Konferenz als anonyme Benutzer behandelt.



Zu einem geplanten Zeitpunkt kann der Besprechungsorganisator den Zugriff auf die Besprechung einschränken, indem er die Besprechung als geschlossen oder gesperrt kennzeichnet. In diesem Fall müssen sich Einwahlbenutzer authentifizieren. Wenn Einwahlbenutzer nicht authentifiziert werden können oder keine Authentifizierung durchführen möchten, werden sie in die Lobby umgeleitet. Sie warten in der Lobby, bis der Besprechungsleiter ihre Teilnahme bestätigt oder ablehnt oder die Verbindung aufgrund einer Zeitüberschreitung getrennt wird. Während der Wartezeit wird für Einwahlbenutzer Musik wiedergegeben. Nachdem Einwahlbenutzer zu einer Konferenz zugelassen wurden, können sie am Audioteil der Konferenz teilnehmen und DTMF-Befehle (Dual-Tone Multi-Frequency, Mehrfrequenzverfahren) über die Telefontastatur ausführen. Besprechungsleiter von Einwahlkonferenzen nutzen DTMF-Befehle zum Steuern, ob sich Teilnehmer selbst stumm schalten können oder nicht, zum Sperren oder Aufheben der Sperrung einer Konferenz, zum Zulassen von Teilnehmern aus der Lobby und zum Ein- und Ausschalten von Ansagen beim Beitreten und Verlassen. Konferenzleiter können mithilfe von DTMF-Befehlen zudem alle Teilnehmer aus der Lobby zulassen. Durch diese Aktion werden die Berechtigungen für die Besprechung so geändert, dass anschließend sämtliche Benutzer zugelassen werden, die der Besprechung beitreten. Alle eingewählten Teilnehmer können DTMF-Befehle ausführen, um Hilfeinformationen abzuhören, die Namen der Teilnehmer wiederzugeben und sich selbst stumm zu schalten.

Für eingewählte Teilnehmer werden unabhängig davon, ob sie sich über das Festnetz einwählen oder nicht, während der Konferenz persönliche Ansagen wiedergegeben. Diese Informationen umfassen z. B., ob die Teilnehmer stumm geschaltet wurden oder nicht, ob die Besprechung aufgezeichnet wird oder ob Benutzer in der Lobby warten.


> [!NOTE]
> Für Teilnehmer, die sich nicht einwählen, sondern der Besprechung über einen Link beitreten, werden keine persönlichen Ansagen wiedergegeben.


