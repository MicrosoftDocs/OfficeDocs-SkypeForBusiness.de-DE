---
title: 'Lync Server 2013: Features von integriertem Unified Messaging'
TOCTitle: Features von integriertem Unified Messaging und Lync Server
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398144(v=OCS.15)
ms:contentKeyID: 49293110
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Features von integriertem Unified Messaging und Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Lync Server 2013, Enterprise-VoIP verwendet die Exchange Unified Messaging (UM)-Infrastruktur, um Funktionen wie Anrufbeantwortung, Anrufbenachrichtigung, Sprachzugriff (einschließlich Voicemail) und Dienste automatischer Telefonzentralen bereitzustellen.

## Anrufbeantwortung

Bei der Anrufbeantwortung werden Sprachnachrichten für Benutzer entgegengenommen, die gerade nicht an ihrem Platz sind oder sich bereits in einem Gespräch befinden. Hierzu gehören die Wiedergabe einer persönlichen Begrüßung, die Aufzeichnung einer Nachricht sowie die Übermittlung der Nachricht, um sie in die Warteschlange für eine Übermittlung an das auf dem Exchange-Postfachserver gespeicherte Postfach des Benutzers einzureihen.

Wenn ein Anrufer eine Nachricht hinterlässt, wird diese an den Posteingang des Benutzers übermittelt. Wenn ein Anrufer keine Nachricht hinterlässt, wird eine Benachrichtigung über einen entgangenen Anruf im Posteingang des Benutzers gespeichert. Benutzer können folgendermaßen auf ihren Posteingang zugreifen: über einen Microsoft Office Outlook-Client für Messaging und Zusammenarbeit, über Outlook Web Access, die Exchange ActiveSync-Technologie oder Outlook Voice Access. Betreff und Priorität von Anrufen können auf ähnliche Weise angezeigt werden wie für E-Mails.

## Outlook Voice Access

Outlook Voice Access ermöglicht Enterprise-VoIP-Benutzern über eine Telefonie-Benutzeroberfläche nicht nur den Zugriff auf Voicemail, sondern auch auf den Posteingang von Exchange, einschließlich E-Mail, Kalender und Kontakte. Die Teilnehmerzugriffsnummer wird von einem Exchange UM-Administrator zugewiesen.

## Automatische Telefonzentrale

Die automatische Telefonzentrale ist eine Exchange UM-Funktion zum Konfigurieren einer Telefonnummer, über die externe Benutzer Unternehmensmitarbeiter erreichen können. Diese Funktion stellt ferner verschiedene Ansagen bereit, die einem externen Anrufer die Navigation in einem Menüsystem ermöglichen. Die Liste der verfügbaren Optionen wird vom Exchange UM-Administrator auf dem Exchange UM-Server konfiguriert.

## Faxdienste

Exchange UM umfasst Faxfunktionen, über die die Benutzer eingehende Faxe in ihren Exchange-Postfächern empfangen können. Ausführliche Informationen zu diesem Thema finden Sie auf der Seite "Unified Messaging" in der Microsoft Exchange Server-Dokumentation unter [http://go.microsoft.com/fwlink/?linkid=135652\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=135652%26clcid=0x407).


> [!NOTE]
> Die Faxdienste des Exchange UM-Servers stehen nicht in Lync Server-Bereistellungen zur Verfügung, die in Microsoft Exchange Server 2010, Exchange 2010 mit dem neuesten Service Pack oder Exchange 2013 integriert sind.


