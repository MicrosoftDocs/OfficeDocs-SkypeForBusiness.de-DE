---
title: Teams Voice Contoso Fallstudie
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
description: Teams Voice Case Study for multi-national corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6ee08fa7bdeb1ded6bda384115a08048021cb67
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918731"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso-Fallstudie: Automatische Telefonkonferenzen und Anrufwarteschleifen

Contoso war mit automatischen Telefonkonferenzen und Anrufwarteschleifen aus der lokalen Skype for Business-Bereitstellung vertraut. Um zu verstehen, wie automatische Telefonkonferenzen in der Cloud und Anrufwarteschleifen eingerichtet werden, haben sie den Plan für automatische Telefonkonferenzen und Anrufwarteschleifen [in Teams überprüft.](plan-auto-attendant-call-queue.md)

## <a name="requirements-depending-on-site-type"></a>Anforderungen je nach Websitetyp

Je nach Websitetyp erfüllte Contoso die folgenden Anforderungen:

- Websitetyp A: Traditionelle Telefoniesysteme 

  Websitetyp A muss die gleiche Telefonnummer haben, die dem Empfang zugeordnet ist wie die Nummer für ihre automatischen Telefonisten. Die Schlüsselabteilungen für jede dieser Websites verfügen über eigene Anrufwarteschleifen, die an Teammitglieder umstellen. Es gab eine Mischung von Websites, die Telefonsystem mit Direct Routing und Telefonsystem mit Anrufplänen verwendeten.  

- Websitetyp B: Skype for Business Enterprise-VoIP 

  Websitetyp B hatte bereits automatische Telefonisten und Anrufwarteschleifen, die zu Teams migriert werden mussten. Contoso musste die Telefonnummern den automatischen Telefon telefonieren zugeordnet lassen. Contoso hat die Meisten dieser Websites auf das Telefonsystem mit Anrufplänen verschoben. An den wenigen Standorten, an denen Anrufpläne nicht verfügbar waren, hat Contoso diese Websites jedoch in eine Direct-Routing-Konfiguration verschoben.  

- Websitetyp C: Skype for Business Enterprise-VoIP & herkömmliches Telefoniesystem 

  Websitetyp C hatte bereits automatische Telefon telefonieren, die sich im herkömmlichen alten Telefoniesystem befinden. Die Entscheidungen und Konfigurationen für diese Website waren identisch mit "Websitetyp A".   

- Für alle Websitetypen hat Contoso die folgenden Fragen gestellt:

  - F: Werden neue oder vorhandene Nummern verwendet? 
    A: Contoso hat beschlossen, vorhandene Telefonnummern zu verwenden, die dem Dienstkonto für die automatische Telefon attendant zugewiesen werden sollen. 

  - F: Wann kann die automatische Telefon attendant eingehende Anrufe annehmen? 
    A: Contoso hat beschlossen, die Geschäftszeiten zu festlegen und Anrufe, die nach Geschäftszeiten eingegangen sind, an eine automatische Telefon attendant "nach Geschäftszeiten" umgeleitet zu lassen.  

  - F: Wie werden die Anrufe an Mitglieder in einer Anrufwarteschleife weiterleiten: Telefonwarteschlange, serielles oder rundes Routing? 
    A: Contoso hat sich entschieden, Attendant Routing zu verwenden, 

  - F: Wie bestimmen wir, wann ein Benutzer einen Anruf erhalten soll oder nicht? 
    A: Contoso hat beschlossen, mithilfe von Anrufbehandlungsoptionen festzustellen, ob der Agent verfügbar ist: anwesenheitsbasiertes Routing. 


## <a name="configuration"></a>Konfiguration

Die Schritte zum Einrichten einer automatischen Telefonkonferenz und einer Anrufwarteschleife umfassen Folgendes unter "Verwalten [von Ressourcenkonten":](manage-resource-accounts.md) 

1. Rufen sie eine Dienstnummer ab. 

2. Beziehen Sie eine kostenlose Telefonsystemlizenz – virtuelle Benutzerlizenz oder eine kostenpflichtige Telefonsystemlizenz für das Ressourcenkonto oder eine Telefonsystemlizenz.

3. Erstellen Sie das Ressourcenkonto. Eine automatische Telefonzentrale oder Anrufwarteschleife muss über ein zugeordnetes Ressourcenkonto verfügen. 

4. Weisen Sie dem Ressourcenkonto das Telefonsystem oder eine Telefonsystem – virtuelle Benutzerlizenz zu. Weitere Informationen finden Sie unter [Microsoft 365 Phone System – Lizenz für virtuelle Benutzer.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)

5. Weisen Sie dem Ressourcenkonto, dem Sie Lizenzen zugewiesen haben, eine Servicetelefonnummer zu. 

6. Erstellen einer Warteschlange oder eine automatische Telefonzentrale für das Telefonsystem 

7. Verknüpfen Sie das Ressourcenkonto mit einer Anrufwarteschleife oder einer automatischen Telefonzentrale. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Websites mit Telefonsystem mit direktem Routing 

Contoso musste die vom lokalen Netzbetreiber bereitgestellte Telefonnummer als Servicenummer in Office 365 einrichten. 

- Zum Einrichten einer telefonnummer, die über Direct Routing verfügbar ist, folgen Sie den Anweisungen unter ["Ressourcenkonten verwalten".](manage-resource-accounts.md) Da Office 365 die lokalen Telefonnummern nicht bekannt ist, hat Contoso PowerShell zum Abschließen des Setups verwendet.   

- Zum Konfigurieren der automatischen Cloud-Attendant hat Contoso die unter "Einrichten einer automatischen [Cloud-Attendant" beschriebenen Schritte befolgt.](create-a-phone-system-auto-attendant.md) 

- Zum Einrichten einer Cloudanrufwarteschleife hat Contoso die unter "Erstellen einer Cloudanrufwarteschleife" [beschriebenen Schritte befolgt.](create-a-phone-system-call-queue.md)  


### <a name="sites-with-phone-system-with-calling-plan"></a>Websites mit Telefonsystem mit Anrufplan

Contoso musste die Telefonnummer, die für automatische Telefonanrufe für Skype for Business Enterprise-VoIP wurde, zu Office 365 Phone System portieren. Dadurch konnte dieselbe Nummer als Servicenummer für die Verwendung als automatische Attendant zugewiesen werden. 

- Um die Telefonnummer zu portieren, folgen Sie den Anweisungen unter "Übertragen von Telefonnummern zu [Teams"](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) und erhielten weitere Anleitungen unter "Verwalten von Telefonnummern [für Ihre Organisation".](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

- Zum Konfigurieren einer automatischen Cloud-Attendant hat Contoso die unter "Einrichten einer automatischen [Cloud-Attendant" beschriebenen Schritte befolgt.](create-a-phone-system-auto-attendant.md)

-  Zum Einrichten einer Cloudanrufwarteschleife hat Contoso die unter "Erstellen einer Cloudanrufwarteschleife" [beschriebenen Schritte befolgt.](create-a-phone-system-call-queue.md)  

 