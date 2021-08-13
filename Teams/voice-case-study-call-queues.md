---
title: 'Teams Contoso-Fallstudie: Automatische Telefonkonferenzen und Anrufwarteschleifen'
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
description: 'Teams Zur Sprachfallstudie für multinationale Unternehmen: Automatische Telefonkonferenzen und Anrufwarteschleifen'
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf1d7a5457af0d7463207c0bdbc9d50433b3142e2f72e7efc7f8c89ade82bc93
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296422"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso-Fallstudie: Automatische Telefonkonferenzen und Anrufwarteschleifen

Contoso war mit automatischen Telefonkonferenzen und Anrufwarteschleifen aus den lokalen Telefonkonferenzen Skype for Business vertraut. Informationen zum Einrichten automatischer Cloud-Telefonkonferenzen und Anrufwarteschleifen wurden unter Planen der Teams von automatischen Telefonkonferenzen und [Anrufwarteschleifen überprüft.](plan-auto-attendant-call-queue.md)

## <a name="requirements-depending-on-site-type"></a>Anforderungen je nach Websitetyp

Je nach Websitetyp erfüllte Contoso die folgenden Anforderungen:

- Websitetyp A: Traditionelle Telefoniesysteme 

  Websitetyp A muss die dem Empfang zugeordnete Telefonnummer wie die Nummer für ihre automatischen Telefonisten behalten. Die Schlüsselabteilungen für jede dieser Websites verfügen über eigene Anrufwarteschleifen, die an Teammitglieder geroutet werden. Es gab eine Mischung von Websites, die Verbindungen Telefonsystem Direct-Routing und Verbindungen Telefonsystem Anrufplänen verwendeten.  

- Websitetyp B: Skype for Business Enterprise-VoIP 

  Websitetyp B bestand aus vorhandenen automatischen Telefonkonferenzen und Anrufwarteschleifen, die zu ihrer Teams. Contoso musste die den automatischen Telefon attendants zugeordneten Telefonnummern behalten. Contoso hat die Mehrzahl dieser Websites auf Telefonsystem Anrufpläne verschoben. An den wenigen Standorten, an denen Anrufpläne nicht verfügbar waren, hat Contoso diese Websites jedoch in eine Direct-Routingkonfiguration verschoben.  

- Site Type C: Skype for Business Enterprise-VoIP & traditional legacy telephony system 

  Der Websitetyp C hatte bereits automatische Telefon telefonieren, die sich im herkömmlichen alten Telefoniesystem befinden. Die Entscheidungen und Konfigurationen für diese Website waren identisch mit Websitetyp A.   

- Für alle Websitetypen hat Contoso die folgenden Fragen gestellt:

  - F: Werden neue oder vorhandene Nummern verwendet? 
    A: Contoso hat beschlossen, vorhandene Telefonnummern zu verwenden, die dem Dienstkonto für die automatische Telefon attendant zugewiesen werden sollen. 

  - F: Wann steht die automatische Telefon attendant zum Annehmen eingehender Anrufe zur Verfügung? 
    A: Contoso hat die Geschäftszeiten festgelegt und Anrufe, die nach Geschäftszeiten eingegangen sind, an eine automatische Telefon attendant "nach Geschäftszeiten" umgeleitet.  

  - F: Wie werden die Anrufe an Mitglieder in einer Anrufwarteschleife weiterleiten: Telefonant, serielles oder rundes Routing? 
    A: Contoso hat sich entschieden, Attendant-Routing zu verwenden, 

  - F: Wie bestimmen wir, wann ein Benutzer einen Anruf erhalten soll oder nicht? 
    A: Contoso hat beschlossen, optionen für die Anrufbehandlung zu verwenden, um festzustellen, ob der Agent verfügbar ist: anwesenheitsbasiertes Routing. 


## <a name="configuration"></a>Konfiguration

Die Schritte zum Einrichten einer automatischen Telefon attendant und einer Anrufwarteschleife umfassen Folgendes unter Verwalten [von Ressourcenkonten:](manage-resource-accounts.md) 

1. Rufen sie eine Dienstnummer ab. 

2. Erhalten Sie eine Telefonsystem - Virtual User-Lizenz oder eine kostenpflichtige Telefonsystem-Lizenz für die Verwendung mit dem Ressourcenkonto oder einer Telefonsystem Lizenz.

3. Erstellen Sie das Ressourcenkonto. Eine automatische Telefonzentrale oder Anrufwarteschleife muss über ein zugeordnetes Ressourcenkonto verfügen. 

4. Weisen Sie dem Ressourcenkonto das Telefonsystem oder eine Telefonsystem – virtuelle Benutzerlizenz zu. Weitere Informationen finden Sie unter [Microsoft 365 Telefonsystem – Virtual User license](./teams-add-on-licensing/virtual-user.md).

5. Weisen Sie dem Ressourcenkonto, dem Sie Lizenzen zugewiesen haben, eine Servicetelefonnummer zu. 

6. Erstellen einer Warteschlange oder eine automatische Telefonzentrale für das Telefonsystem 

7. Verknüpfen Sie das Ressourcenkonto mit einer Anrufwarteschleife oder einer automatischen Telefonzentrale. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Websites mit Telefonsystem Direct-Routing 

Contoso musste die vom lokalen Netzbetreiber bereitgestellte Telefonnummer als Servicenummer in der App Office 365. 

- Zum Einrichten einer Telefonnummer, die über Direct-Routing verfügbar ist, folgen Sie den Anweisungen unter Verwalten von [Ressourcenkonten.](manage-resource-accounts.md) Da Office 365 die lokalen Telefonnummern nicht kennen, hat Contoso PowerShell zum Abschließen des Setups verwendet.   

- Zum Konfigurieren der automatischen Cloud-Attendant hat Contoso die unter Einrichten einer automatischen [Cloud-Attendant beschriebenen Schritte befolgt.](create-a-phone-system-auto-attendant.md) 

- Zum Einrichten einer Cloud-Anrufwarteschleife hat Contoso die unter Erstellen einer [Cloud-Anrufwarteschleife](create-a-phone-system-call-queue.md)beschriebenen Schritte befolgt.  


### <a name="sites-with-phone-system-with-calling-plan"></a>Websites mit Telefonsystem Anrufplan

Contoso musste die Telefonnummer, die für automatische Skype for Business Enterprise-VoIP verwendet wurde, zu Office 365-Telefonsystem. Dadurch konnte dieselbe Nummer als Servicenummer für die Verwendung als automatische Attendant zugewiesen werden. 

- Zum Portieren der Telefonnummer hat Contoso die Anweisungen unter Übertragen von Telefonnummern zu [Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) weitere Anleitungen unter Verwalten von Telefonnummern [für Ihre Organisation erhalten.](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Zum Konfigurieren einer automatischen Cloud-Attendant hat Contoso die unter Einrichten einer automatischen [Cloud-Attendant beschriebenen Schritte befolgt.](create-a-phone-system-auto-attendant.md)

-  Zum Einrichten einer Cloud-Anrufwarteschleife hat Contoso die unter Erstellen einer [Cloud-Anrufwarteschleife](create-a-phone-system-call-queue.md)beschriebenen Schritte befolgt.  

