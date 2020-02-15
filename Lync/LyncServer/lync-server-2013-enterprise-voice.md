---
title: Lync Server 2013 Enterprise-VoIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8f0aef4d3f2323bcfcd99f42b265ea02b6126b2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a>Enterprise-VoIP in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-04-08_

Mit Enterprise-VoIP bietet lync Server ein eigenständiges VoIP-Angebot (Voice over Internet Protocol) zum Erweitern oder ersetzen herkömmlicher Nebenstellenanlagen (Private Branch Exchange, Nebenstellenanlage). Enterprise-VoIP-Benutzer können Kollegen im VoIP-Netzwerk oder in der Nebenstellenanlage Ihrer Organisation anrufen, und Sie können herkömmliche Telefonnummern außerhalb Ihrer Organisation anrufen. Die Enterprise-VoIP-Lösung umfasst allgemeine Anruffunktionen wie Antwort, Weiterleitung, Übertragung, Aufbewahrung, Umleitung, Freigabe und Parken sowie erweiterte 9-1-1 (E9-1-1)-Anrufe (E9-1-1 ist nur in den USA verfügbar.) Enterprise-VoIP unterstützt auch eine Vielzahl von aktuellen und älteren IP-und USB-Geräten.

<div>

## <a name="placing-and-receiving-calls"></a>Platzieren und empfangen von Anrufen

Mithilfe von lync können Benutzer Anrufe tätigen, indem Sie einen Namen oder eine Telefonnummer auf der Tastatur eingeben oder eine Wähltastatur auf dem Bildschirm verwenden. Benutzer können Anrufe auch direkt aus der Kontaktliste initiieren. Sie können auch lync Phone Edition-Geräte bereitstellen, bei denen es sich um eigenständige IP-Telefongeräte handelt, die von Microsoft-Partnern bereitgestellt werden.

Benutzer können mehrere Telefongeräte bei lync Server registriert haben und problemlos zwischen ihnen wechseln können.

Benutzer werden auf allen Geräten gleichzeitig auf eingehende Anrufe mit anpassbaren Klingeltönen auf IP-Telefongeräten und einer Benachrichtigung ähnlich einer Sofortnachricht auf Ihrem PC aufmerksam gemacht.

Benutzer können auch eine einzelne Telefonnummer festlegen, die eine Verbindung zu Ihrem Telefon, PC und Mobiltelefon herstellt, sodass Sie unabhängig von ihrer Position erreicht werden können.

</div>

<div>

## <a name="basic-call-features"></a>Grundlegende Anruffunktionen

Während eines Anrufs kann ein Benutzer zusätzliche eingehende Anrufe beantworten oder ausgehende Anrufe initiieren, und der vorhandene aktive Anruf wird automatisch in den Haltestatus versetzt. Anrufe können von einem Benutzer zu einem anderen übertragen werden, entweder direkt oder nachdem der erste Benutzer mit dem zweiten Benutzer privat gesprochen hat. Benutzer können auch Anrufe an ein anderes Gerät übertragen; Beispielsweisekönnten Sie einen aktiven Anruf an Ihr Mobiltelefon übertragen, wenn Sie die Tür ihres Büros verlassen.

</div>

<div>

## <a name="richer-communications"></a>Umfassendere Kommunikation

Wenn Sie mit einem anderen Benutzer mit lync kommunizieren, können Benutzer dem Anruf problemlos Text, Video oder Desktopfreigaben hinzufügen. Das Feature "do-not-Disturb" ist in die Anwesenheitseinstellungen in lync integriert.

Mit Exchange Unified Messaging (um) können lync und lync Server in Microsoft Exchange Server 2013 und Microsoft Outlook 2013 integriert werden. Benutzer können sehen, ob Sie neue Voicemails sowohl in Ihrem lync-Fenster als auch in e-Mail haben. Während Sie in der e-Mail klicken, können Sie die Voicemail-Audiodaten in einer e-Mail-Nachricht wiedergeben oder ein Transkript der Voicemailnachricht anzeigen.

</div>

<div>

## <a name="advanced-calling-features"></a>Erweiterte Anruffunktionen

Enterprise-VoIP umfasst auch mehrere erweiterte Anruffunktionen wie lync-Anrufdelegierung, Teamanrufe, gruppenanrufannahme und Reaktionsgruppen.

Mit der lync-Anrufdelegierung können Benutzer die Anrufbehandlung an einen oder mehrere Assistenten delegieren, indem Sie die Einstellungen für die **Anrufweiterleitung**für **Tools** \> **** \> aufrufen. Der Stellvertreter kann mehrere Anruf Aufgaben im Namen des Benutzers ausführen, einschließlich der Überprüfung von anrufen, das Platzieren von Anrufen und das Initiieren von Konferenzen.

<div>


> [!IMPORTANT]  
> Möglicherweise suchen Sie nach einer anderen ähnlich benannten Funktion, der lync-Kalender Delegierung. Sie erfordert nicht die Enterprise-VoIP-Funktion und ermöglicht Benutzern das Planen von Online-lync-Besprechungen in Outlook. Wenn Sie hier auf der Suche nach diesen Informationen sind, empfehlen wir das Auschecken von "CsClientPolicy", um Informationen zum Aktivieren der Exchange-Delegat <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">-</A> Synchronisierung zu erhalten.



</div>

Team Anrufe ermöglichen es einem Benutzer, eingehende Anrufe gleichzeitig an den Telefonen von Teamkollegen zu klingeln, damit alle Personen im Team den Anruf annehmen können.

Group Call Pickup, ein neues Feature in kumulierten Updates für lync Server 2013: Februar 2013, ermöglicht Benutzern, eingehende Anrufe an Ihre Kollegen von ihren eigenen Telefonen aus zu beantworten. Die gruppenanrufannahme unterscheidet sich von der Team Berufung in erster Linie dadurch, dass ein eingehender Anruf nur am Telefon des beabsichtigten Empfängers klingelt, aber jeder andere Benutzer kann ihn über die Wahl einer Gruppennummer für die Anrufannahme wählen.

Reaktionsgruppen können für Warteschlangen und intelligent weiterleiten von Anrufen an designierte Agents eingerichtet werden. Häufige Verwendungen sind IT-Helpdesks, Hotlines für Personalwesen und andere interne Kontakt Center.

</div>

<div>

## <a name="enterprise-voice-administration"></a>Enterprise-VoIP-Verwaltung

Lync Server verwendet Standards und veröffentlichte Schnittstellen, um mit der vorhandenen Infrastruktur zusammenzuarbeiten. Es unterstützt sowohl Gateway-als auch SIP-Optionen (beispielsweise SIP-Trunking) für die Zusammenschaltung mit IP-Nebenstellen Systemen und den PSTN-Netzwerken, sodass Sie Benutzer über einen Zeitraum zu Enterprise-VoIP migrieren und gleichzeitig die Unterbrechungen minimieren können. Lync Server unterstützt herkömmliche Codecs wie g. 711, g. 722 und g. 723.1 für die Interoperabilität mit herkömmlichen VoIP-Lösungen.

Mit der Anrufsteuerung (Call Admission Control, CAC) können Administratoren Beschränkungen für den lync Server von Sprach-und Videodaten Verkehr für eingeschränkte Netzwerkverbindungen festlegen und die Aktion angeben, die ausgeführt werden soll, wenn ein neuer Anruf den Höchstwert überschreitet. Die Aktionen können Routing durch einen alternativen Pfad einschließen oder den Anruf ablehnen.

Lync Server arbeitet mit Survivable Branch-Appliances von Drittanbietern zusammen, um lokale Anrufdienste und Verbindungen mit PSTN in Zweigniederlassungen bereitzustellen, falls ein WAN-Fehler am zentralen Standort vorliegt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

