---
title: Microsoft-Telefonie-Lösungen
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Beschreibt Microsoft-Telefonie-Lösungen.
ms.openlocfilehash: 57d1abe69bc0513fa015543e8440e9d9f778b78c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160329"
---
# <a name="microsoft-telephony-solutions"></a>Microsoft-Telefonie-Lösungen

Microsoft unterstützt mehrere Optionen, wenn Sie Ihre Reise zu Microsoft Teams in der Microsoft-Cloud beginnen. In diesem Artikel können Sie entscheiden, welche Microsoft-Telefonielösung (Telefon System in der Cloud oder Enterprise-VoIP lokal) für Benutzer in Ihrer Organisation geeignet ist und wie Ihre Organisation eine Verbindung mit dem Telefon Festnetz (Public Switched Telephone Network, PSTN) herstellen kann. 

Verwenden Sie diesen Artikel zusammen mit dem dazugehörigen technischen Diagramm, das eine visuelle Hilfe für die richtige Entscheidungsfindung für Ihre Organisation bietet:

- [Microsoft Telephony Solutions – PDF](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.pdf)

- [Microsoft-Telefonlösungen – Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.vsdx)




## <a name="private-branch-exchange-pbx-options"></a>PBX-Optionen (Private Branch Exchange)

### <a name="phone-system-office-365"></a>Telefon System (Office 365)
  
Telefon System ist die Technologie von Microsoft, mit der die Funktionen für die Anrufsteuerung und die PBX-Funktionen (Private Branch Exchange) in der Office 365 Cloud mit Microsoft Teams und/oder Skype for Business Online aktiviert werden können. 

Telefon System kann mit Teams oder Skype for Business Online-Clients und zertifizierten Geräten verwendet werden. Mit dem Telefon System können Sie Ihr vorhandenes PBX-System durch eine Reihe von Features ersetzen, die direkt von Office 365 bereitgestellt werden und eng in die Cloud-Produktivitäts Erfahrung des Unternehmens integriert sind. Um Telefon System mit dem Telefon Festnetz (Public Switched Telephone Network, PSTN) zu verbinden, können Sie den Anrufplan von Microsoft oder ihren eigenen Telefon Träger auswählen.

Weitere Informationen finden Sie unter [Was ist Telefon System in Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/what-is-phone-system-in-office-365).

### <a name="enterprise-voice-skype-for-business-server"></a>Enterprise-VoIP (Skype for Business Server)

Enterprise-VoIP ist die Technologie von Microsoft für die Aktivierung der Anrufsteuerung und von PBX-Funktionen (Private Branch Exchange) im lokalen Skype for Business Server. Diese Option kann nur über ihren eigenen Telefon Träger mit dem öffentlichen Telefonnetz verbunden werden. 

Weitere Informationen finden Sie unter [Plan for Enterprise Voice in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

## <a name="connection-to-the-public-switched-telephone-network-pstn-options"></a>Verbindung zu den PSTN-Optionen (Public Switched Telephone Network)

Sie können eine Verbindung mit dem Telefon Festnetz (Public Switched Telephone Network, PSTN) herstellen, indem Sie Folgendes auswählen:

- Verwenden des Microsoft-Anruf Plans in Office 365 
- Verbinden Ihres eigenen Telefon Trägers

### <a name="calling-plan-office-365"></a>Aufruf Plan (Office 365)

Diese Option verbindet das Office 365 Telefon System von Microsoft mit dem Telefon Festnetz (Public Switched Telephone Network, PSTN), um Anrufe an fest Netzgeräte und Mobiltelefone auf der ganzen Welt zu ermöglichen. Mit dem Anrufplan ist Microsoft Ihr PSTN-Carrier.

Weitere Informationen finden Sie unter [Aufruf Pläne für Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/calling-plans-for-office-365).

### <a name="connect-your-own-telephony-carrier-office-365-and-skype-for-business-on-premises"></a>Verbinden Ihres eigenen Telefonie-Carriers (Office 365 und Skype for Business lokal)

Mit dieser Option wird entweder das Telefonsystem in Office 365 oder das Enterprise-VoIP-System in Skype for Business lokal mit Ihrem Telefonie-Netzwerk verbunden. Für diese Option ist ein unterstützter Session Border Controller (SBC) erforderlich. In einigen Fällen erfordert diese Option möglicherweise zusätzliche Microsoft-Software, die lokal bereitgestellt wird.

## <a name="which-solution-is-right-for-your-organization"></a>Welche Lösung ist für Ihre Organisation geeignet?

Sie können eine All-in-the-Cloud-Lösung, eine Connect-your-own-Carrier-Lösung oder eine Mischung zwischen all-in-the-Cloud-und Drittanbieter-Carriern auswählen:

- Telefon System mit Anruf Plan (alle in der Cloud)

- Telefon System mit eigenem Carrier über direktes Routing

- Telefon System mit eigenem Carrier über Skype for Business Server oder Cloud Connector Edition

- Enterprise-VoIP in Skype for Business Server mit eigenem Anbieter

Die von Ihnen gewählte Lösung hängt von ihren aktuellen und zukünftigen Anforderungen ab, beispielsweise:

- Unabhängig davon, ob Sie die von Ihrer lokalen Bereitstellung bereitgestellte Funktionalität beibehalten möchten oder müssen.
- Der Client, den Sie für Ihre Benutzer bereitstellen möchten.
- Was ist Ihr Plan für das Verschieben von Personen in die Cloud?
- Ob Sie mit PBX-Anlagen von Drittanbietern und anderen Telefongeräten zusammenarbeiten müssen.

Prüfen Sie die folgenden Fragen, um die beste Lösung für Ihre Organisation zu ermitteln:

- Verfügen Sie über eine vorhandene Skype for Business Server-Bereitstellung?
- Werden Ihre Benutzer in Skype for Business lokal, in der Cloud auf Skype for Business Online oder beides verwaltet? 
- Möchten Sie lokale Benutzer in die Cloud migrieren?
- Ist der PSTN-Anrufplan von Microsoft in Ihrer Region verfügbar?
- Möchten oder müssen Sie Ihren aktuellen Telefonanbieter Behalten?  Müssen Sie beispielsweise Ihren aktuellen Carrier aufgrund eines vorhandenen Vertrags behalten?
- Verfügen Sie über eine vorhandene lokale Legacy-PBX-Anlage, die Sie behalten möchten oder müssen?
- Bietet Ihre aktuelle Legacy-PBX-Anlage eindeutige Funktionen, die für Ihr Unternehmen entscheidend sind?
- Benötigen einige oder alle Benutzerfunktionen, die derzeit im Telefon System nicht angeboten werden?

Beachten Sie Folgendes:

- Alle vier Optionen können nebeneinander vorhanden sein, falls Sie eine Lösung für eine komplexe Umgebung entwerfen oder die Migration in mehreren Schritten verwalten müssen.
- Telefon System mit eigenem Carrier über Skype for Business Server oder Cloud Connector Edition kann nur mit Skype for Business Server oder Cloud Connector bereitgestellt werden. Koexistenz von Skype for Business Server und Cloud Connector wird in einem einzelnen Unternehmen nicht unterstützt.

## <a name="phone-system-with-calling-plan"></a>Telefon System mit Anruf Plan


Telefon System mit Anrufplan ist eine All-in-the-Cloud-Option für Teams oder Skype for Business Online Benutzer, wie im folgenden Diagramm dargestellt:

![Telefon System mit Anruf Plan](../../sfbserver2019/media/msft-telephony-solutions-1.png)


- Microsoft Phone System mit hinzugefügten inländischen oder internationalen Anrufplänen, die das Anrufen von Telefonen auf der ganzen Welt ermöglichen (je nachdem, welche Stufe der Dienst lizenziert wird). 
- Da der PSTN-Anrufplan von Office 365 ausgeht, ist für diese Option keine Bereitstellung oder Wartung einer lokalen Bereitstellung erforderlich.
- Kunden können einen unterstützten SBC über Direct Routing für die Interoperabilität mit PBX-Anlage, analogen Geräten und anderen von der SBC unterstützten 3rd Party-Telefongeräten verbinden.

| Infrastrukturanforderungen                   | Pflichtfeld?|
| :----------------------------------------------------| ---------:|
| Erfordert eine unterbrechungsfreie Verbindung mit Office 365 | Ja |
| Weltweit verfügbar *                            | Nein  |
| Erfordert die Bereitstellung und Verwaltung eines unterstützten Session Border Controller (SBC) | Nein |
| Erfordert Vertrag mit Drittanbieter-Carrier      | Nein   |
| Erfordert die Bereitstellung und Verwaltung von Skype for Business Server oder Cloud Connector Edition | Nein |

\*Weitere Informationen über die Länder, in denen der Anrufplan verfügbar ist, finden Sie unter [Verfügbarkeit von Ländern und Regionen für Audiokonferenzen und Anrufpläne](https://docs.microsoft.com/en-us/MicrosoftTeams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).


Wenn Sie die folgenden Fragen mit "Ja" beantworten, ist dies die richtige Lösung für Sie:

- Anrufplan ist in Ihrer Region verfügbar.
- Sie müssen Ihren aktuellen PSTN-Carrier nicht beibehalten.
- Sie möchten den von Microsoft verwalteten Zugriff auf das Telefon Festnetz (Public Switched Telephone Network, PSTN) verwenden.
- Sie möchten keine Session Border Controller selbst verwalten.
- Teams und/oder Skype for Business Online verfügt über alle Funktionen, die Ihre Organisation benötigt.

Weitere Informationen finden Sie unter [Was ist Telefon System in Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/what-is-phone-system-in-office-365) und [Anrufpläne für Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/calling-plans-for-office-365).

## <a name="phone-system-with-own-carrier-via-direct-routing"></a>Telefon System mit eigenem Carrier über direktes Routing

Mit dieser Option wird Microsoft Phone System in der Cloud mit nahezu jedem Telefonie-Carrier für Teams-Benutzer bereitgestellt.

![Telefon System mit Ihrem Carrier über direktes Routing](../../sfbserver2019/media/msft-telephony-solutions-2.png)

- Verbinden Sie Ihren eigenen unterstützten SBC direkt mit dem Microsoft Phone System, ohne dass zusätzliche lokale Software benötigt wird.  
- Verwenden Sie praktisch alle Telefonie-Carrier mit Microsoft Phone System.
- Kann von Kunden oder von Ihrem Carrier oder Partner konfiguriert und verwaltet werden (Fragen Sie, ob Ihr Carrier oder Partner diese Option bereitstellt).
- Konfigurieren Sie die Interoperabilität zwischen ihren Telefongeräten (beispielsweise einer PBX-Anlage eines Drittanbieters und analogen Geräten) und Microsoft Phone System.

| Infrastrukturanforderungen                   | Pflichtfeld?|
| :----------------------------------------------------| ---------:|
| Erfordert eine unterbrechungsfreie Verbindung mit Office 365 | Ja |
| Weltweit verfügbar                            | Ja  |
| Erfordert die Bereitstellung und Verwaltung eines unterstützten Session Border Controller (SBC) | Ja |
| Erfordert Vertrag mit Drittanbieter-Carrier *      | Ja   |
| Erfordert die Bereitstellung und Verwaltung von Skype for Business Server oder Cloud Connector Edition | Nein |

\*Sofern nicht als Option bereitgestellt, um eine Verbindung mit einer Drittanbieter-Nebenstellenanlage, analogen Geräten oder anderen Telefonieanlagen für Benutzer bereitzustellen, die sich im Telefon System mit Anrufplänen befinden.

Wenn Sie die folgenden Fragen mit "Ja" beantworten, ist dies die richtige Lösung für Sie:

- Sie möchten Microsoft Teams mit dem Telefon System verwenden.
- Sie müssen Ihren aktuellen PSTN-Carrier beibehalten.
- Sie möchten das Routing mischen, einige Anrufe werden über Anrufpläne durchlaufen, einige über Ihren Carrier
- Sie müssen mit PBX-Anlagen und/oder Geräten von Drittanbietern zusammenarbeiten, wie US-Overhead-Pagers, analoge Geräte
- Teams verfügt über alle Funktionen, die Ihre Organisation benötigt.

Weitere Informationen finden Sie unter [Was ist Telefon System in Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/what-is-phone-system-in-office-365) und [Planen des direkten Routings](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-plan).


## <a name="phone-system-with-own-carrier-via-skype-for-business-server-or-cloud-connector-edition"></a>Telefon System mit eigenem Carrier über Skype for Business Server oder Cloud Connector Edition

Mit dieser Option wird Microsoft Phone System in der Cloud mit einer Verbindung zu einem lokalen Telefonie-Netzwerk für Skype for Business Online Benutzer bereitgestellt.

![Telefon System mit Ihrem Carrier über Skype for Business Server oder Cloud Connector Edition](../../sfbserver2019/media/msft-telephony-solutions-3.png)

 - Verbinden Sie Ihren eigenen unterstützten SBC mit dem Microsoft Phone System über Skype for Business Server oder Skype for Business Cloud Connector Edition, die lokal bereitgestellt wurde. 
- Verwenden Sie praktisch alle Telefonie-Carrier mit Microsoft Phone System. 
- Wenn Sie bereits Skype for Business Server lokal haben, können Sie es nutzen;  Wenn dies nicht der Fall ist, können Sie eine leichtere Version bereitstellen – Cloud Connector Edition.


| Infrastrukturanforderungen                   | Pflichtfeld?|
| :----------------------------------------------------| ---------:|
| Erfordert eine unterbrechungsfreie Verbindung mit Office 365 | Ja |
| Weltweit verfügbar                            | Ja  |
| Erfordert die Bereitstellung und Verwaltung eines unterstützten Session Border Controller (SBC) | Ja |
| Erfordert Vertrag mit Drittanbieter-Carrier      | Ja   |
| Erfordert die Bereitstellung und Verwaltung von Skype for Business Server oder Cloud Connector Edition | Ja |



Wenn Sie die folgenden Fragen mit "Ja" beantworten, ist dies die richtige Lösung für Sie:

- Sie möchten Skype for Business Online für Ihre Benutzer verwenden.
- Der Plan für PSTN-Anrufe ist in Ihrer Region nicht verfügbar.
- Sie müssen Ihren aktuellen PSTN-Carrier beibehalten.

Weitere Informationen finden Sie unter [Was ist Telefon System in Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/what-is-phone-system-in-office-365), [Skype for Business Server 2019](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-server-2019)und [Plan for Skype for Business Cloud Connector Edition](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Empfehlung: Wenn sich Geschäftsbedingungen ändern – beispielsweise müssen Sie Ihren PSTN-Carrier nicht mehr aufbewahren – ziehen Sie es vor, mit den Optionen 1 oder 2 zu Microsoft Teams zu wechseln, um Folgendes zu tun:
- Minimieren der Wartungskosten
- Zugriff auf die neuesten von Microsoft veröffentlichten Features

## <a name="enterprise-voice-in-skype-for-business-server-with-own-carrier"></a>Enterprise-VoIP in Skype for Business Server mit eigenem Anbieter

Mit dieser Option wird Enterprise-VoIP lokal mit einer Verbindung zu einem lokalen Telefonie-Netzwerk für Skype for Business lokale Benutzer bereitgestellt.

![Enterprise-VoIP in Skype for Business Server mit eigenem Anbieter](../../sfbserver2019/media/msft-telephony-solutions-4.png)

- Verbinden Sie Ihren eigenen unterstützten SBC mit Enterprise-VoIP-System in Skype for Business lokalen Server.
- Verwenden Sie diese, wenn Sie eine lokale Überlebensfähigkeit benötigen.
- Verwenden Sie praktisch alle Telefonie-Carrier mit Microsoft Phone System. 
- Komplexeste Option für die Bereitstellung und Verwaltung.

| Infrastrukturanforderungen                   | Pflichtfeld?|
| :----------------------------------------------------| ---------:|
| Erfordert eine unterbrechungsfreie Verbindung mit Office 365 | Nein |
| Weltweit verfügbar                            | Ja  |
| Erfordert die Bereitstellung und Verwaltung eines unterstützten Session Border Controller (SBC) | Ja |
| Erfordert Vertrag mit Drittanbieter-Carrier      | Ja   |
| Erfordert die Bereitstellung und Verwaltung von Skype for Business Server | Ja |

Weitere Informationen finden Sie unter [Plan for Enterprise Voice in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

Empfehlung: Wenn sich Geschäftsbedingungen ändern – beispielsweise müssen Sie Ihren PSTN-Carrier nicht mehr aufbewahren – ziehen Sie es vor, mit den Optionen 1 oder 2 zu Microsoft Teams zu wechseln, um Folgendes zu tun:
- Minimieren der Wartungskosten
- Zugriff auf die neuesten von Microsoft veröffentlichten Features











  
