---
title: Front-End-Server-VoIP-Komponenten für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: Informieren Sie sich über die Enterprise-VoIP-Komponenten, die sich auf Front-End-Servern in Skype for Business Server befinden, einschließlich Übersetzungsdienst und verschiedene Routingkomponenten.
ms.openlocfilehash: d28beb809e172ea5d778e0cf8273cb232b7cf67c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276852"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>Front-End-Server-VoIP-Komponenten für Skype for Business Server

Informieren Sie sich über die Enterprise-VoIP-Komponenten, die sich auf Front-End-Servern in Skype for Business Server befinden, einschließlich Übersetzungsdienst und verschiedene Routingkomponenten.

Die VoIP-Komponenten, die sich auf Front-End-Servern befinden, sind wie folgt:

- Übersetzungsdienst

- Eingangsroutingkomponente

- Ausgangsroutingkomponente

- Routingkomponente für Exchange UM

- Komponente für das clusterübergreifende Routing

- [Vermittlungsserver Komponente in Skype for Business Server](mediation-server.md)

## <a name="translation-service"></a>Übersetzungsdienst

Der Übersetzungsdienst ist die Serverkomponente, die eine gewählte Nummer gemäß den vom Administrator definierten Normalisierungsregeln in das E.164-Format oder ein anderes Format übersetzt. Der Übersetzungsdienst kann in andere Formate als E.164 übersetzen, wenn in Ihrer Organisation ein privates Nummernsystem oder ein Gateway bzw. eine Nebenstellenanlage verwendet wird, das bzw. die E.164 nicht unterstützt.

## <a name="inbound-routing-component"></a>Eingangsroutingkomponente

Die eingehende Routing Komponente verarbeitet eingehende Anrufe weitgehend gemäß den Einstellungen, die von Benutzern auf Ihren Enterprise-VoIP-Clients angegeben werden. Diese Komponente unterstützt außerdem das Delegieren von Anrufen und das gleichzeitige Klingeln, sofern dies vom Benutzer konfiguriert ist. Beispielsweise geben Benutzer an, ob unbeantwortete Anrufe weitergeleitet oder lediglich zur Benachrichtigung protokolliert werden sollen. Wenn die Anrufweiterleitung aktiviert ist, können Benutzer angeben, ob nicht angenommene Anrufe an eine andere Nummer oder an einen Exchange um-Server weitergeleitet werden sollen, der für die Anrufannahme konfiguriert wurde. Die eingehende Routing Komponente wird standardmäßig auf allen Standard Edition-Server-und-Front-End-Servern installiert.

## <a name="outbound-routing-component"></a>Ausgangsroutingkomponente

Die Ausgangsroutingkomponente leitet Anrufe an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weiter. Es wendet Anruf Autorisierungsregeln, wie Sie in der VoIP-Richtlinie des Benutzers definiert sind, an Anrufer an und bestimmt das optimale PSTN-Gateway für die Weiterleitung jedes Anrufs. Die ausgehende Routing Komponente wird standardmäßig auf allen Standard Edition-Server-und-Front-End-Servern installiert.

Die Ausgangsroutingkomponente verwendet eine Routinglogik, die größtenteils von Netzwerk- oder Telefonieadministratoren gemäß den Anforderungen ihrer Organisationen konfiguriert wird.

## <a name="exchange-um-routing-component"></a>Routingkomponente für Exchange UM

Die Exchange um-Routingkomponente verarbeitet das Routing zwischen Skype for Business Server und Servern, auf denen Exchange Unified Messaging (um) ausgeführt wird, um Skype for Business Server mit Unified Messaging-Funktionen zu integrieren.

Die Exchange um-Routingkomponente behandelt auch das Umleiten von Voicemail über das PSTN, wenn Exchange um-Server nicht verfügbar sind. Wenn Sie über Enterprise-VoIP-Benutzer an Zweigstellen verfügen, die nicht über eine stabile WAN-Verbindung zu einem zentralen Standort verfügen, bietet die Survivable Branch-Appliance, die Sie auf der Zweigstelle bereitstellen, die Voicemail-Überlebensfähigkeit von Zweig Benutzern während eines WAN-Ausfalls. Wenn die WAN-Verbindung nicht verfügbar ist, führt die Survivable Branch-Appliance die folgenden Aktionen aus:

- Nicht beantwortete Anrufe werden über das Telefonfestnetz an den Exchange Unified Messaging-Server am zentralen Standort weitergeleitet

- Benutzer haben die Möglichkeit, Voicemailnachrichten über das Telefonfestnetz abzurufen

- Benachrichtigungen zu verpassten Anrufen werden in einer Warteschlange platziert und auf den Exchange UM-Server hochgeladen, wenn die WAN-Verbindung wieder verfügbar ist.

Zum Aktivieren des Umleitens von Voicemail empfehlen wir, dass Ihr Exchange-Administrator die automatische Exchange UM-Telefonzentrale (AA) so konfiguriert, dass nur Nachrichten akzeptiert werden.

Ausführliche Informationen zu diesen Funktionen finden Sie unter [On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) bzw. [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx).

## <a name="intercluster-routing-component"></a>Komponente für das clusterübergreifende Routing

Die InterCluster-Routingkomponente ist für das Weiterleiten von Anrufen an den primären Registrierungspool des anrufenden verantwortlich. Wenn dies nicht möglich ist, leitet die Komponente den Anruf an den sicherungsregistrierungspool des berufenen weiter. Wenn die primären und Sicherungs registrierungspools des berufenen über das IP-Netzwerk nicht erreichbar sind, leitet die InterCluster-Routingkomponente den Anruf über das PSTN an die Telefonnummer des Benutzers weiter.

## <a name="other-front-end-server-components-required-for-voip"></a>Andere für VoIP erforderliche Front-End-Serverkomponenten

Andere Komponenten, die sich auf dem Front-End-Server oder Director befinden und die grundlegende Unterstützung für VoIP bieten, aber nicht selbst VoIP-Komponenten sind, umfassen Folgendes:

- **Benutzerdienste.** Die Benutzerdienste führen eine umgekehrte Nummernsuche für die Zielrufnummer jedes eingehenden Anrufs durch und ordnen diese Nummer dem SIP-URI des Zielbenutzers zu. Mithilfe dieser Informationen verteilt die eingehende Routing Komponente den Anruf an die registrierten SIP-Endpunkte des Benutzers. Benutzer Dienste ist eine Hauptkomponente auf allen Front-End-Servern und-Directors.

- **Benutzerreplikationsdienst** Extrahiert Benutzer Telefonnummern aus Active Directory-Domänendiensten und schreibt Sie in Tabellen in der RTC-Datenbank, wo Sie für Benutzer Dienste und den Adressbuch Server verfügbar sind. Der Benutzerreplikationsdienst ist eine Hauptkomponente auf allen Front-End-Servern.

- **Adressbuchserver.** Enthält Informationen zur globalen Adressliste aus Active Directory-Domänendiensten für Skype for Business Server-Clients. Sie ruft auch Benutzer-und Kontaktinformationen aus der RTC-Datenbank ab, schreibt die Informationen in die Adressbuchdateien und speichert die Dateien dann in einem freigegebenen Ordner, in dem Sie von Skype for Business-Clients heruntergeladen werden. Der Adressbuch Server schreibt die Informationen in die RTCAb-Datenbank, die vom Adressbuch-Webabfrage Dienst zur Beantwortung von Benutzer Suchabfragen von Skype for Business Mobile verwendet wird. Optional werden Unternehmensbenutzer-Telefonnummern, die in die RTC-Datenbank geschrieben wurden, zum Zweck der Bereitstellung von Benutzerkontakten in Skype for Business normalisiert. Der Adressbuchdienst wird standardmäßig auf allen Front-End-Servern installiert. Der Adressbuch-Webabfrage Dienst wird standardmäßig mit den Webdiensten auf den einzelnen Front-End-Servern installiert.


