---
title: 'Lync Server 2013: Enterprise-VoIP'
TOCTitle: Enterprise-VoIP
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg417163(v=OCS.15)
ms:contentKeyID: 49295398
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enterprise-VoIP in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-04-08_

Mit Enterprise-VoIP stellt Lync Server eine eigenständige Voice over IP-Lösung (VoIP) zum Erweitern oder Ersetzen herkömmlicher Nebenstellensysteme (Private Branch Exchange, PBX) bereit. Enterprise-VoIP-Benutzer können Kollegen im VoIP-Netzwerk oder Nebenstellensystem Ihrer Organisation anrufen oder Anrufe an herkömmliche Telefonnummern außerhalb der Organisation tätigen. Die Enterprise-VoIP-Lösung umfasst gängige Anruffunktionen wie das Beantworten, Weiterleiten, Übergeben, Halten, Umleiten, Fortsetzen und Parken von Anrufen sowie E9-1-1-Anrufe. (Die E9-1-1-Funktion ist nur in den Vereinigten Staaten verfügbar.) Enterprise-VoIP unterstützt außerdem eine umfangreiche Palette an modernen und älteren IP- und USB-Geräten.

## Tätigen und Annehmen von Anrufen

Mit Lync können Benutzer Anrufe tätigen, indem sie einen Namen oder eine Telefonnummer auf ihrer Tastatur oder einer auf dem Bildschirm angezeigten Wähltastatur eingeben. Benutzer können Anrufe auch direkt über ihre Kontaktlisten tätigen. Sie können ferner auch Lync Phone Edition-Geräte bereitstellen, bei denen es sich um eigenständige IP-Telefongeräte handelt, die von Microsoft-Partnern bereitgestellt werden.

Benutzer können mehrere Telefongeräte für Lync Server registrieren und problemlos zwischen diesen Geräten wechseln.

Benutzer werden über eingehende Anrufe simultan auf allen Geräten benachrichtigt. Die Benachrichtigung erfolgt hierbei auf IP-Telefongeräten mithilfe anpassbarer Klingeltöne, auf dem PC wird eine Benachrichtigung ähnlich einer Chatnachricht angezeigt.

Benutzer können auch eine einzige Telefonnummer für Tischtelefon, PC und Mobiltelefon festlegen, sodass sie unabhängig von ihrem Standort jederzeit erreichbar sind.

## Grundlegende Anruffunktionen

Während eines Anrufs kann ein Benutzer zusätzliche eingehende Anrufe beantworten oder ausgehende Anrufe einleiten. Der zuvor eingegangene aktive Anrufe wird in diesem Fall automatisch in einer Warteschleife platziert. Anrufe können von einem Benutzer an einen anderen übergeben werden, entweder direkt oder nach privater Rücksprache des ersten Benutzers mit dem zweiten Benutzer. Benutzer können Anrufe auch an ein anderes Gerät weiterleiten. Beispielsweise kann ein aktiver Anruf auf das Mobiltelefon übertragen werden, wenn der Benutzer im Begriff ist, das Büro zu verlassen.

## Vielfältigere Kommunikation

Während eines Gesprächs mit einem anderen Benutzer über Lync kann auf einfache Weise die Übertragung von Text oder Videodaten oder die Desktopfreigabe aktiviert werden. Die Nicht stören-Funktion ist in die Anwesenheitseinstellungen von Lync integriert.

Exchange Unified Messaging (UM) ermöglicht die Integration von Lync und Lync Server in Microsoft Exchange Server 2013 und Microsoft Outlook 2013. Benutzer können sowohl im Lync-Fenster als auch anhand ihrer E-Mails sehen, ob neue Voicemailnachrichten eingegangen sind. In der E-Mail-Anwendung können sie auf die Nachricht klicken, um die Voicemail als Audiodatei abzuspielen oder eine Transkription der Voicemailnachricht anzuzeigen.

## Erweiterte Anruffunktionen

Enterprise-VoIP umfasst darüber hinaus verschiedene erweiterte Anruffunktionen, darunter Delegierung, Teamanrufe, Gruppenanrufannahme und Reaktionsgruppen.

Mithilfe der Delegierung können Benutzer die Anrufabwicklung an einen oder mehrere Assistenten delegieren. Die Stellvertretung kann verschiedene Anrufaufgaben im Namen des Benutzers ausführen, darunter das Ablehnen nicht erwünschter Anrufe, das Tätigen von Anrufen sowie das Initiieren von Konferenzen.

Die Teamanruffunktion ermöglicht es einem Benutzer, für eingehende Anrufe ein simultanes Klingeln auf den Telefonen von Teamkollegen zu aktivieren, sodass jedes Teammitglied den Anruf entgegennehmen kann.

Mit dem neuen Gruppenanrufannahme-Feature, das mit den kumulativen Updates für Lync Server 2013 vom Februar 2013 eingeführt wurde, können Benutzer die eingehenden Anrufe ihrer Kollegen auf den eigenen Telefonen entgegennehmen. Die Gruppenanrufannahme unterscheidet sich von der Teamanruffunktion hauptsächlich darin, dass bei einem eingehenden Anruf nur das Telefon des jeweiligen Empfängers klingelt. Jeder andere im Team kann den Anruf aber beantworten, indem er eine Nummer für die Anrufannahme wählt.

Reaktionsgruppen können eingerichtet werden, um Anrufe in Warteschleifen zu platzieren und für eine intelligente Weiterleitung an dedizierte Agents zu sorgen. Zu den häufigsten Einsatzbereichen dieser Funktionen zählen IT-Helpdesks, Hotlines der Personalabteilung und andere interne Kontaktcenter.

## Enterprise-VoIP-Verwaltung

Lync Server verwendet Standards und öffentliche Schnittstellen zur Interaktion mit der vorhandenen Infrastruktur. Es werden sowohl Gateway- als auch SIP-Optionen (z. B. SIP-Trunking) für die Verbindung mit IP-Nebenstellensystemen und dem Festnetz unterstützt, sodass sie Benutzer nach und nach und mit minimaler Unterbrechung zu Enterprise-VoIP migrieren können. Lync Server unterstützt herkömmliche Codecs wie G.711, G.722 und G.723.1, um Interoperabilität mit herkömmlichen VoIP-Lösungen zu gewährleisten.

Mithilfe der Anrufsteuerung können Administratoren Grenzwerte für die Menge an Sprach- und Videodaten festlegen, die Lync Server über beschränkte Netzwerkverbindungen sendet. Sie können auch die Aktion festlegen, die durchgeführt werden soll, wenn ein neuer Anruf den festgelegten Grenzwert überschreiten würde. Mögliche Aktionen sind beispielsweise das Routing an einen alternativen Pfad oder eine Zurückweisung des Anrufs.

Lync Server arbeitet mit Survivable Branch Appliances von Drittanbietern, um bei einem WAN-Ausfall am zentralen Standort lokale Anrufdienste bereitzustellen und die Festnetzverbindung in Zweigstellenbüros sicherzustellen.

