---
title: 'Teams Contoso-Fallstudie: Automatische Telefonzentralen und Anrufwarteschleifen'
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
description: 'Teams Voice Case Study für multinationale Unternehmen: Automatische Telefonzentralen und Anrufwarteschleifen'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c0b6da7bf00fd4e62cf3e9b3b08074bf1b42788
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681716"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso-Fallstudie: automatische Telefonzentralen und Anrufwarteschleifen

Contoso war mit automatischen Telefonzentralen und Anrufwarteschleifen aus ihrer lokalen Skype for Business Bereitstellung vertraut. Um zu verstehen, wie automatische Cloudtelefonzentralen und Anrufwarteschleifen eingerichtet werden, haben sie [den Plan für Teams automatischen Telefonzentralen und Anrufwarteschleifen](plan-auto-attendant-call-queue.md) überprüft.

## <a name="requirements-depending-on-site-type"></a>Anforderungen je nach Websitetyp

Je nach Websitetyp hatte Contoso die folgenden Anforderungen:

- Websitetyp A: Herkömmliche Legacy-Telefoniesysteme 

  Websitetyp A, der benötigt wird, um dieselbe Telefonnummer beizubehalten, die dem Empfangsmitarbeiter zugeordnet ist, wie die Nummer für die automatischen Telefonzentralen. Die wichtigsten Abteilungen für jede dieser Websites hätten eigene Anrufwarteschleifen, die an Teammitglieder weitergeleitet würden. Es gab eine Mischung aus Standorten, die Telefonsystem mit Direct Routing und Telefonsystem mit Anrufplänen verwendet haben.  

- Websitetyp B: Skype for Business Enterprise-VoIP 

  Websitetyp B verfügte über vorhandene automatische Telefonzentralen und Anrufwarteschleifen, die zu Teams migriert werden mussten. Contoso musste die Telefonnummern beibehalten, die den automatischen Telefonzentralen zugeordnet sind. Contoso hat die Meisten dieser Websites in Telefonsystem mit Anrufplänen verschoben. An den wenigen Orten, an denen Anrufpläne nicht verfügbar waren, hat Contoso diese Websites jedoch in eine Direct Routing-Konfiguration verschoben.  

- Websitetyp C: Skype for Business Enterprise-VoIP & herkömmliches Legacy-Telefoniesystem 

  Standorttyp C verfügte über vorhandene automatische Telefonzentralen, die sich im herkömmlichen älteren Telefoniesystem befinden. Die Entscheidungen und Konfigurationen für diese Website waren identisch mit Websitetyp A.   

- Für alle Websitetypen stellte Contoso die folgenden Fragen:

  - F: Werden neue oder vorhandene Nummern verwendet? 
    Antwort: Contoso hat sich entschieden, vorhandene Telefonnummern zu verwenden, die dem Dienstkonto für die automatische Telefonzentrale zugewiesen werden. 

  - F: Wann steht die automatische Telefonzentrale zur Annahme eingehender Anrufe zur Verfügung? 
    Antwort: Contoso hat beschlossen, Geschäftszeiten festzulegen und Anrufe, die nach den Geschäftszeiten eingehen, an eine automatische Telefonzentrale "nach Feierabend" umgeleitet zu lassen.  

  - F: Wie werden die Anrufe an Mitglieder in einer Anrufwarteschleife weitergeleitet: Telefonzentrale, serielles Routing oder Roundrobin-Routing? 
    A: Contoso hat sich für die Verwendung des Telefonzentralenroutings entschieden, 

  - F: Wie werden wir feststellen, wann ein Benutzer einen Anruf erhalten soll oder nicht? 
    Antwort: Contoso entschied sich für die Verwendung von Anrufbehandlungsoptionen, um festzustellen, ob der Agent verfügbar ist: anwesenheitsbasiertes Routing. 


## <a name="configuration"></a>Konfiguration

Die Schritte zum Einrichten einer automatischen Telefonzentrale und einer Anrufwarteschleife umfassen Folgendes, das in ["Ressourcenkonten verwalten"](manage-resource-accounts.md) beschrieben ist: 

1. Rufen sie eine Dienstnummer ab. 

2. Rufen Sie eine kostenlose Telefonsystem – virtuelle Benutzerlizenz oder eine kostenpflichtige Telefonsystemlizenz ab, die mit dem Ressourcenkonto oder einer Telefonsystemlizenz verwendet werden soll.

3. Erstellen Sie das Ressourcenkonto. Eine automatische Telefonzentrale oder Anrufwarteschleife muss über ein zugeordnetes Ressourcenkonto verfügen. 

4. Weisen Sie dem Ressourcenkonto das Telefonsystem oder eine Telefonsystem – virtuelle Benutzerlizenz zu. Weitere Informationen finden Sie [unter Microsoft 365 Telefonsystem – Virtuelle Benutzerlizenz](./teams-add-on-licensing/virtual-user.md).

5. Weisen Sie dem Ressourcenkonto, dem Sie Lizenzen zugewiesen haben, eine Diensttelefonnummer zu. 

6. Erstellen einer Warteschlange oder eine automatische Telefonzentrale für das Telefonsystem 

7. Verknüpfen Sie das Ressourcenkonto mit einer Anrufwarteschleife oder einer automatischen Telefonzentrale. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Websites mit Telefonsystem mit Direct Routing 

Contoso musste die vom lokalen Netzbetreiber bereitgestellte Telefonnummer als Servicenummer in Office 365 einrichten. 

- Um eine über Direct Routing verfügbare Telefonnummer einzurichten, hat Contoso die Anweisungen unter ["Ressourcenkonten verwalten"](manage-resource-accounts.md) befolgt. Da Office 365 die lokalen Telefonnummern nicht kennt, verwendete Contoso PowerShell, um die Einrichtung abzuschließen.   

- Um die automatische Cloud-Telefonzentrale zu konfigurieren, hat Contoso die unter ["Einrichten einer automatischen Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md)" beschriebenen Schritte ausgeführt. 

- Zum Einrichten einer Cloudanrufwarteschleife hat Contoso die unter [Erstellen einer Cloud-Anrufwarteschleife](create-a-phone-system-call-queue.md) beschriebenen Schritte ausgeführt.  


### <a name="sites-with-phone-system-with-calling-plan"></a>Websites mit Telefonsystem mit Anrufplan

Contoso musste die Telefonnummer, die für Skype for Business Enterprise-VoIP automatischen Telefonzentralen verwendet wurde, zu Office 365-Telefonsystem portieren. Dadurch konnte dieselbe Nummer als Dienstnummer für die Verwendung als automatische Telefonzentrale zugewiesen werden. 

- Um die Telefonnummer zu portieren, folgte Contoso den Anweisungen in ["Telefonnummern übertragen" zu Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) und erhielt zusätzliche Anleitungen unter ["Telefonnummern für Ihre Organisation verwalten](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)".

- Um eine automatische Cloudtelefonzentrale zu konfigurieren, hat Contoso die unter ["Einrichten einer automatischen Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md)" beschriebenen Schritte ausgeführt.

-  Zum Einrichten einer Cloudanrufwarteschleife hat Contoso die unter [Erstellen einer Cloud-Anrufwarteschleife](create-a-phone-system-call-queue.md) beschriebenen Schritte ausgeführt.  

