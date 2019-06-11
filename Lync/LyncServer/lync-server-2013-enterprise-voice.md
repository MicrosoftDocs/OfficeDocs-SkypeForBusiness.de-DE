---
title: 'Lync Server 2013: Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7c8131c2f52dfc7ab061d8dec46ee34b62f89e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a>Enterprise-VoIP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-04-08_

Mit Enterprise-VoIP bietet lync Server ein eigenständiges VoIP-Angebot (Voice over Internet Protocol) zum verbessern oder ersetzen herkömmlicher PBX-Systeme (Private Branch Exchange). Enterprise-VoIP-Benutzer können Kollegen im VoIP-Netzwerk oder in der Telefonanlage Ihrer Organisation anrufen, und Sie können herkömmliche Telefonnummern außerhalb Ihrer Organisation anrufen. Die Enterprise-VoIP-Lösung umfasst allgemeine Anruffunktionen wie Answer, Forward, Transfer, halten, umleiten, freigeben und Parken sowie erweiterte 9-1-1 (E9-1-1)-Anrufe (E9-1-1 ist nur in den Vereinigten Staaten verfügbar.) Enterprise-VoIP unterstützt auch eine breite Palette an aktuellen und älteren IP-und USB-Geräten.

<div>

## <a name="placing-and-receiving-calls"></a>Tätigen und empfangen von Anrufen

Mithilfe von lync können Benutzer Anrufe tätigen, indem Sie auf der Tastatur einen Namen oder eine Telefonnummer eingeben oder eine Wähltastatur verwenden, die auf dem Bildschirm angezeigt wird. Benutzer können Anrufe auch direkt aus Ihrer Kontaktliste initiieren. Sie können auch lync Phone Edition-Geräte bereitstellen, bei denen es sich um eigenständige IP-Telefongeräte handelt, die von Microsoft-Partnern bereitgestellt werden.

Benutzer können mehrere Telefongeräte haben, die bei lync Server registriert sind, und können problemlos zwischen ihnen wechseln.

Benutzer werden auf allen ihren Geräten gleichzeitig auf eingehende Anrufe aufmerksam gemacht, mit anpassbaren Klingeltönen auf IP-Telefongeräten und einer Benachrichtigung, die mit einer Sofortnachricht auf dem PC vergleichbar ist.

Benutzer können auch eine einzelne Telefonnummer einrichten, die eine Verbindung zu Ihrem Tischtelefon, PC und Mobiltelefon herstellt, damit Sie unabhängig von Ihrem Aufenthaltsort erreicht werden können.

</div>

<div>

## <a name="basic-call-features"></a>Grundlegende Anruffunktionen

Während eines Anrufs kann ein Benutzer weitere eingehende Anrufe annehmen oder ausgehende Anrufe initiieren, und der vorhandene aktive Anruf wird automatisch in Wartestellung gesetzt. Anrufe können von einem Nutzer zu einem anderen übertragen werden, entweder direkt oder nachdem der erste Nutzer privat mit dem zweiten Nutzer gesprochen hat. Benutzer können auch Anrufe an ein anderes Gerät übertragen. So könnten Sie beispielsweise einen aktiven Anruf an Ihr Mobiltelefon übertragen, während Sie die Tür zu Ihrem Büro verlassen.

</div>

<div>

## <a name="richer-communications"></a>Reichere Kommunikation

Wenn Sie mit einem anderen Benutzer mit lync sprechen, können Benutzer dem Anruf einfach Text-, Video-oder Desktopfreigaben hinzufügen. Das Feature "nicht stören" ist in die Anwesenheitseinstellungen in lync integriert.

Mit Exchange Unified Messaging (um) können lync und lync Server mit Microsoft Exchange Server 2013 und Microsoft Outlook 2013 integriert werden. Benutzer können sehen, ob Sie über neue Voicemails verfügen, sowohl in Ihrem lync-Fenster als auch in der e-Mail-Nachricht. In der e-Mail können Sie in einer e-Mail-Nachricht klicken, um die Audiowiedergabe wiederzugeben, oder Sie können eine Aufzeichnung der Voicemail-Nachricht anzeigen.

</div>

<div>

## <a name="advanced-calling-features"></a>Erweiterte Anruffunktionen

Enterprise-VoIP umfasst mehrere erweiterte Anruffunktionen, wie etwa die lync-Anrufdelegierung, Teamanrufe, Gruppenanruf Abholung und Antwortgruppen.

Mit der lync-Anrufdelegierung können Benutzer die Anrufbehandlung an einen oder mehrere Assistenten delegieren, indem Sie die Einstellungen für die **** \> **Anrufweiterleitung**der **Tools** \> aufrufen. Die Stellvertretung kann mehrere Anruf Aufgaben im Namen des Benutzers durchführen, einschließlich von Screening-anrufen, anrufen und Initiieren von Konferenzen.

<div>


> [!IMPORTANT]  
> Möglicherweise suchen Sie nach einem anderen ähnlich benannten Feature, der lync-Kalender Delegierung. Sie erfordert keine Enterprise-VoIP-Funktion und ermöglicht Benutzern, Online-lync-Besprechungen aus Outlook zu planen. Wenn Sie auf der Suche nach diesen Informationen sind, empfehlen wir Ihnen, <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">CsClientPolicy</A> zu lesen, um Informationen zum Aktivieren der Synchronisierung von Exchange-Stellvertretungen zu erhalten.



</div>

Mit Team anrufen kann ein Benutzer mit eingehenden Anrufen gleichzeitig die Telefone von Teamkollegen anrufen, damit jeder im Team den Anruf annehmen kann.

Der Gruppenanruf Pickup, ein neues Feature in kumulativen Updates für lync Server 2013: Februar 2013, ermöglicht Benutzern, eingehende Anrufe von ihren eigenen Telefonen an Ihre Kollegen zu beantworten. Die Abholung von Gruppen anrufen unterscheidet sich von Team anrufen in erster Linie dadurch, dass ein eingehender Anruf nur auf dem Telefon des beabsichtigten Empfängers klingelt, jeder andere Benutzer aber eine Anrufannahme-Gruppennummer wählen kann.

Reaktionsgruppen können für Warteschlangen und Intelligentes Routing von Anrufen an bestimmte Agents eingerichtet werden. Häufige Verwendungen sind IT-Helpdesks, Personal-Hotlines und andere interne Contact Center.

</div>

<div>

## <a name="enterprise-voice-administration"></a>Enterprise-VoIP-Verwaltung

Lync Server verwendet Standards und veröffentlichte Schnittstellen für die Interoperabilität mit der vorhandenen Infrastruktur. Sie unterstützt sowohl Gateway-als auch SIP-Optionen (beispielsweise SIP-Trunking) für die Verbindung zu IP-PBX-Systemen und den PSTN-Netzwerken, sodass Sie Benutzer im Laufe der Zeit zu Enterprise-VoIP migrieren können, während die Unterbrechungen minimiert werden. Lync Server unterstützt herkömmliche Codecs wie g. 711, g. 722 und g. 723.1 für die Interoperabilität mit herkömmlichen VoIP-Lösungen.

Mit der Anrufannahme Steuerung (CAC) können Administratoren Grenzwerte für den Sprach-und Videodatenverkehr von lync-Servern festlegen, die auf eingeschränkten Netzwerk Links durchgeführt werden, und die Aktion angeben, die ausgeführt werden soll, wenn ein neuer Anruf den Höchstbetrag überschreitet. Die Aktionen können das Routing durch einen alternativen Pfad oder das ablehnen des Anrufs umfassen.

Lync Server arbeitet mit Drittanbietern überlebensfähiger Branch-Appliances, um lokale Anrufdienste und eine Verbindung zu PSTN an Zweigstellen bereitzustellen, falls ein WAN-Fehler am zentralen Standort vorliegt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

