---
title: 'Teams Contoso-Fallstudie: Notrufe'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 'Teams Fallstudie für multinationale Unternehmen: Notrufe'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69231adb4588039012cceec1063571ddc201c2bb
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587474"
---
# <a name="contoso-case-study-emergency-calling"></a>Contoso-Fallstudie: Notrufe

Informationen zur Verfügbarkeit von Notrufen und der Terminologie für Notrufe Notfalladresse, Ort, Notfallstandort und registrierte Adresse Contoso hat die Informationen unter Verwalten von Notrufen und Planen und Konfigurieren von dynamischen Notrufen &mdash; &mdash; [überprüft.](configure-dynamic-emergency-calling.md) [](what-are-emergency-locations-addresses-and-call-routing.md)

In Office 365 wird ein Anrufplanbenutzer automatisch für Notrufe aktiviert. Aber nur Anrufplanbenutzer in den USA können dynamische Standorte für die Weiterleitung von Notrufen verwenden. 

Für Direct-Routing hat Contoso erfahren, dass zusätzliche Konfiguration für das Routing von Notrufen und möglicherweise für Partnerkonnektivität erforderlich ist. Der Administrator muss die Verbindung mit einem ERSP (Emergency Routing Service Provider) (VEREINIGTE Staaten) KONFIGURIEREN ODER den Session Border Controller (SBC) für eine ELIN-Anwendung (Emergency Location Identification Number) konfigurieren.

Contoso hat Niederlassungen in den USA und außerhalb der USA:

- In den USA können Benutzer des Contoso-Anrufplans dynamische Standorte für das Routing von Notrufen verwenden. 

- Außerhalb der USA verfügt Contoso über einige Websites, die Anrufpläne verwenden, und einige Websites, die über direktes Routing Telefonsystem Verbindung zu diesen Websites sind.

## <a name="emergency-calling-use-cases"></a>Einsatzfälle für Notrufe

Nach der Entscheidung, wie Contoso eine Verbindung mit dem Telefon Herstellen einer Verbindung herstellen soll, hat Contoso die folgenden Einsatzfälle für Notrufe identifiziert: 

- [Anrufplanbenutzer in den USA](#calling-plan-user-in-the-united-states) 

- [Anrufplanbenutzer außerhalb der USA](#calling-plan-user-outside-of-the-united-states)

- [Benutzer, der über Direct-Routing Telefonsystem Verbindung zu einer Verbindung herstellt](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>Anrufplanbenutzer in den USA  

Es gibt Anforderungen, wann die Telefonnummer einem Notfallstandort zugeordnet werden muss. Um diese Anforderungen zu verstehen, hat Contoso [Überlegungen für Anrufpläne überprüft.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) 

Aufgrund dieser Anforderungen hat Contoso beschlossen, den Standort der Telefonnummer zuzuordnen, wenn einem Benutzer in den USA eine Nummer zugewiesen wird.

### <a name="calling-plan-user-outside-of-the-united-states"></a>Anrufplanbenutzer außerhalb der USA 

Um zu verstehen, wann eine Telefonnummer einem Notfallstandort zugeordnet werden muss, hat Contoso Überlegungen [für Anrufpläne überprüft.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) Auf der Grundlage der Anforderungen hat Contoso folgende Punkte entschieden:  

-  Contoso wird den Standort der Telefonnummer zuordnen, wenn einem Benutzer in Kanada eine Nummer zugewiesen wird. 

- Contoso weist einen Notfallstandort zu, wenn die Telefonnummer von Office 365 oder übertragen wird, wenn eine Nummer von einem anderen Dienstanbieter oder Netzbetreiber übertragen wird. 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>Benutzer, der über Direct-Routing Telefonsystem Verbindung zu einer Verbindung herstellt 

Zum Planen des Notfallroutings für diesen Einsatzfall hat Contoso Überlegungen [für Direct-Routing überprüft.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing) Da Benutzer von Direct Routing Notrufe nicht auf die gleiche Weise wie Anrufplanbenutzer erhalten, musste Contoso entscheiden, wie Notrufe erfolgen sollten. Direktes Routing kann mit einem ErSP (Emergency Routing Service Provider) verbunden werden. Direct Routing kann auch über einen SBC verfügen, der eine Notfallstandortidentifikationsnummer (Emergency Location Identification Number, ELIN) enthält.   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>Überlegungen zum Notfall-Routingdienstanbieter (Emergency Routing Service Provider, ERSP)

Die Anbieter für Notfallroutingdienste können Notrufe automatisch basierend auf der Position des Anrufers weiterleiten.  

- Wenn ein Anbieter für Notfallroutingdienste in eine Direct Routing-Bereitstellung integriert ist, werden Notrufe mit dynamisch angeschafften Standort automatisch an den öffentlichen Sicherheits-Antwortpunkt (Public Safety Answering Point, PSAP) geroutet, der diese Position einnimmt. 

- Notrufe ohne dynamisch erfassten Standort werden zuerst angezeigt, um den aktuellen Standort des Benutzers zu ermitteln, bevor der Anruf anhand des aktualisierten Standorts mit der entsprechenden Rettungszentrale verbunden wird. 


#### <a name="elin-considerations"></a>Überlegungen zum ELIN

Wenn eine SBC ELIN-Anwendung in eine Direct Routing-Bereitstellung integriert ist, müssen zusätzliche Konfigurationsschritte erfolgen, um die Notfalladressen Telefonnummern zuzuordnen.  

Contoso hat beschlossen, Session Border Controller zu verwenden, die ELIN-Anwendungen (Emergency Location Identification Number) enthalten.  

## <a name="security-desk-notification"></a>Benachrichtigung des Security Desk

Die Möglichkeit, die Sicherheitsleitzahl zu benachrichtigen, wenn ein Notruf ein gestellt wird, steht sowohl für Microsoft-Anrufpläne als Telefonsystem Direct Routing zur Verfügung. Contoso überprüfte die Details in der Benachrichtigung des Security Desk, um festzustellen, ob dies in den Büros konfiguriert werden sollte.  

Contoso hat sich entschieden, die Benachrichtigung des Security Desk zu verwenden.

## <a name="configuration"></a>Konfiguration 

Contoso hat die Schritte unter [Konfigurieren dynamischer Notrufe für](configure-dynamic-emergency-calling.md) folgende Dinge befolgt: 

- Zuweisen von Notfalladressen 

- Konfigurieren von Netzwerkeinstellungen 

- Konfigurieren des Informationsdiensts für den Standort 

- Konfigurieren von Notfallrichtlinien 

- Aktivieren von Benutzern und Websites 

- Testen von Notrufen 

Nach der Konfiguration dynamischer Notrufe musste Contoso den Standort dem entsprechenden Benutzer zuweisen.  

- Zum Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation hat Contoso die Schritte unter Hinzufügen, Ändern oder Entfernen eines Notfallstandorts [für Ihre Organisation befolgt.](add-change-remove-emergency-location-organization.md)

- Zum Erstellen von Orten für Gebäude, Stockwerke und Büros hat Contoso die Schritte unter Hinzufügen, Ändern oder Entfernen eines Orts [für einen Notfallstandort befolgt.](add-change-remove-emergency-place-organization.md) 

- Zum Zuweisen eines Notfallstandorts hat Contoso die Schritte unter Zuweisen oder [Ändern eines Notfallstandorts für einen Benutzer befolgt.](assign-change-emergency-location-user.md) 

 
