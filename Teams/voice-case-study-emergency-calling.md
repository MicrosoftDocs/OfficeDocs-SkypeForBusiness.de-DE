---
title: Teams Voice Contoso-Fallstudie
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
description: Teams Voice Case Study für Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786028"
---
# <a name="contoso-case-study-emergency-calling"></a>Contoso-Fallstudie: Notrufe

Um die Verfügbarkeit von Notrufen und Terminologie für Notrufe in Notfällen, &mdash; Ort, Notfall Standort und registrierte Adresse zu verstehen, hat &mdash; contoso die Verwaltung von [Notrufen](what-are-emergency-locations-addresses-and-call-routing.md) und die [Planung und Konfiguration dynamischer Notrufe](configure-dynamic-emergency-calling.md)überprüft.

In Office 365 wird ein Nutzer des Anruf Plans automatisch für Notrufe aktiviert. Aber nur Anruf Plan Benutzer in den Vereinigten Staaten können dynamische Speicherorte für die Weiterleitung von Notrufen verwenden. 

Für das direkte Routing hat Contoso erfahren, dass für das Routing von Notrufen und möglicherweise für die Partner Konnektivität eine zusätzliche Konfiguration erforderlich ist. Der Administrator muss die Verbindung mit einem Notverwaltungsdienste (Emergency Routing Service Provider, ERSP) (USA) konfigurieren oder den Session Border Controller (SBC) für eine Emergency Location Identification Number (Elin)-Anwendung konfigurieren.

Contoso hat Niederlassungen in den USA und außerhalb der Vereinigten Staaten:

- In den Vereinigten Staaten können die Benutzer des Contoso-Anruf Plans dynamische Speicherorte für die Weiterleitung von Notrufen verwenden. 

- Außerhalb der USA verfügt Contoso über einige Websites, die Anrufpläne und einige Websites verwenden, die über direktes Routing mit dem Telefon System verbunden sind.

## <a name="emergency-calling-use-cases"></a>Notfall Anruf-Anwendungsfälle

Nach der Entscheidung, wie Contoso eine Verbindung mit dem Telefonsystem herstellen wird, erkannte Contoso die folgenden Anwendungsfälle für Notfälle: 

- [Benutzer des Anruf Plans in den Vereinigten Staaten](#calling-plan-user-in-the-united-states) 

- [Anruf Plan Benutzer außerhalb der Vereinigten Staaten](#calling-plan-user-outside-of-the-united-states)

- [Benutzer, der über direktes Routing eine Verbindung mit dem Telefon System herstellt](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>Benutzer des Anruf Plans in den Vereinigten Staaten  

Es gibt Anforderungen, wenn die Telefonnummer einem Notfall Standort zugeordnet werden muss. Um diese Anforderungen zu verstehen, hat Contoso [Überlegungen für Anrufpläne](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)überprüft. 

Basierend auf diesen Anforderungen beschloss contoso, den Standort mit der Telefonnummer zu verknüpfen, wenn eine Nummer einem Benutzer in den USA zugewiesen wurde.

### <a name="calling-plan-user-outside-of-the-united-states"></a>Anruf Plan Benutzer außerhalb der Vereinigten Staaten 

Um zu verstehen, wann eine Telefonnummer einem Notfall Standort zugeordnet werden muss, hat Contoso [Überlegungen für Anrufpläne](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)überprüft. Basierend auf den Anforderungen beschloss Contoso Folgendes:  

-  Contoso ordnet den Standort mit der Telefonnummer zu, wenn einem Benutzer in Kanada eine Nummer zugewiesen wird. 

- Contoso weist einen Notfall Standort zu, wenn die Telefonnummer von Office 365 abgerufen wird oder wenn eine Nummer von einem anderen Dienstanbieter oder Netzbetreiber übertragen wird. 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>Benutzer, der über direktes Routing eine Verbindung mit dem Telefon System herstellt 

Zum Planen des Notfall Routings für diesen Anwendungsfall hat Contoso [Überlegungen zur direkten Weiterleitung](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)überprüft. Da die Benutzer des direkten Routings keine Notrufe auf die gleiche Weise wie Anruf Plan Benutzer erhalten, musste Contoso entscheiden, wie Notrufe bereitgestellt werden sollen. Direktes Routing kann mit einem Notfall-Routingdienst Anbieter (ERSP) verbunden werden. Das direkte Routing kann auch einen SBC aufweisen, der eine Notfall Standort-Identifikationsnummer (Elin) enthält.   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>Überlegungen zu ERSP (Emergency Routing Service Provider)

Die Notverwaltungsdienste (Emergency Routing Service Providers, ERSPs) können Notrufe automatisch basierend auf dem Standort des Anrufers weiterleiten.  

- Wenn ein Notfall-Routing-Service-Anbieter in eine direkte Routing-Bereitstellung integriert ist, werden Notrufe mit einem dynamisch erworbenen Standort automatisch an den öffentlichen Sicherheits Beantwortungs Punkt (PSAP) weitergeleitet, der diesem Standort dient. 

- Notrufe ohne dynamisch erworbenen Standort werden zuerst angezeigt, um den aktuellen Standort des Benutzers zu ermitteln, bevor der Anruf mit dem entsprechenden Dispatch Center basierend auf dem aktualisierten Standort verbunden wird. 


#### <a name="elin-considerations"></a>Elin-Überlegungen

Wenn eine SBC Elin-Anwendung in eine Direct Routing-Bereitstellung integriert ist, müssen zusätzliche Konfigurationsschritte ausgeführt werden, um die Notfalladressen mit Telefonnummern zu verknüpfen.  

Contoso hat entschieden, Sitzungs Grenz Controller zu verwenden, die Elin-Anwendungen (Emergency Location Identification Number) enthalten.  

## <a name="security-desk-notification"></a>Benachrichtigung über Sicherheits Desk

Die Möglichkeit, den Security Desk zu benachrichtigen, wenn ein Notruf getätigt wird, steht sowohl für Microsoft-Anrufpläne als auch für das direkte Routing des Telefonsystems zur Verfügung. Contoso hat die Details in der Security Desk-Benachrichtigung überprüft, um festzustellen, ob dies in ihren Büros konfiguriert werden sollte.  

Contoso hat entschieden, die Benachrichtigung über das Sicherheits Desk zu verwenden.

## <a name="configuration"></a>Konfiguration 

Contoso befolgte die Schritte unter [Konfigurieren von dynamischen Notrufen](configure-dynamic-emergency-calling.md) an: 

- Notfalladressen zuweisen 

- Konfigurieren von Netzwerkeinstellungen 

- Konfigurieren des Standort Informationsdiensts 

- Konfigurieren von Notfall Richtlinien 

- Aktivieren von Benutzern und Websites 

- Testen von Notrufen 

Nach der Konfiguration des dynamischen Notrufs musste Contoso den Standort dem entsprechenden Benutzer zuweisen.  

- Zum Hinzufügen, ändern oder Entfernen eines Notfall Standorts für Ihre Organisation folgte Contoso den Schritten unter [hinzufügen, ändern oder Entfernen eines Notfall Standorts für Ihre Organisation](add-change-remove-emergency-location-organization.md) .

- Zum Erstellen von Orten für Gebäude, Etagen und Büros folgte Contoso den Schritten unter [hinzufügen, ändern oder Entfernen eines Orts für einen Notfall Standort](add-change-remove-emergency-place-organization.md) . 

- Um einen Notfall Standort zuzuweisen, befolgte Contoso die Schritte unter [zuweisen oder Ändern eines Notfall Standorts für einen Benutzer](assign-change-emergency-location-user.md). 

 