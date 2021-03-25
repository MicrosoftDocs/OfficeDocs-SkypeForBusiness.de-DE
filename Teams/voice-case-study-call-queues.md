---
title: Fallstudie "Teams voice Contoso"
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
description: Sprachfallstudie zu Teams für multinationale Unternehmen
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cb8029a8f4e979a76afe069ee9b22e7be897913
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121293"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso-Fallstudie: Automatische Telefonwarteschlangen und Anrufwarteschlangen

Contoso war mit automatischen Telefonkonferenzen und Anrufwarteschlangen aus der lokalen Skype for Business-Bereitstellung vertraut. Um zu verstehen, wie Sie automatische Cloud-Telefonwarteschlangen und Anrufwarteschlangen einrichten, haben sie sich die Automatischen Telefonwarteschlangen und [Anrufwarteschlangen](plan-auto-attendant-call-queue.md)für Teams geplant.

## <a name="requirements-depending-on-site-type"></a>Anforderungen je nach Websitetyp

Je nach Websitetyp hatte Contoso die folgenden Anforderungen:

- Websitetyp A: Herkömmliche ältere Telefoniesysteme 

  Websitetyp A erforderlich, um dieselbe Telefonnummer zu behalten, die dem Empfanger zugeordnet ist, wie die Nummer für die automatischen Telefonanrufe. Die wichtigsten Abteilungen für jede dieser Websites verfügen über eigene Anrufwarteschlangen, die an Teammitglieder gesendet werden. Es gab eine Mischung aus Websites, die Telefonsystem mit Direct Routing und Telefonsystem mit Anrufplänen verwendeten.  

- Websitetyp B: Skype for Business Enterprise-VoIP 

  Websitetyp B hatte vorhandene automatische Telefonkonferenzen und Anrufwarteschlangen, die zum Migrieren zu Teams erforderlich waren. Contoso musste die Telefonnummern behalten, die den automatischen Telefonanrufen zugeordnet sind. Contoso hat die meisten dieser Websites mit Anrufplänen in das Telefonsystem verschoben. An den wenigen Standorten, an denen Anrufpläne nicht verfügbar waren, hat Contoso diese Websites jedoch in eine Direct Routing-Konfiguration verschoben.  

- Websitetyp C: Skype for Business Enterprise-VoIP & herkömmliches älteres Telefoniesystem 

  Websitetyp C hatte vorhandene automatische Telefonanten, die sich im herkömmlichen älteren Telefoniesystem befinden. Die Entscheidungen und Konfigurationen für diese Website waren identisch mit Websitetyp A.   

- Für alle Websitetypen hat Contoso die folgenden Fragen gestellt:

  - F: Werden neue oder vorhandene Zahlen verwendet? 
    A: Contoso hat beschlossen, vorhandene Telefonnummern zu verwenden, um dem Dienstkonto für die automatische Telefonwarte zugewiesen zu werden. 

  - F: Wann steht die automatische Telefonwarte zur Annahme eingehender Anrufe zur Verfügung? 
    A: Contoso hat beschlossen, die Geschäftszeiten festzu legen und Anrufe, die nach Geschäftszeiten empfangen wurden, an eine automatische Telefonwarte "nach den Stunden" umgeleitet zu lassen.  

  - F: Wie werden die Anrufe an Mitglieder in einer Anrufwarteschlange gesendet: Telefonleitung, serielles Routing oder Round-Robin-Routing? 
    A: Contoso hat sich entschieden, das Routing "Attendant" zu verwenden, 

  - F: Wie wird ermittelt, wann ein Benutzer einen Anruf erhalten soll oder nicht? 
    A: Contoso hat entschieden, die Anrufbehandlungsoptionen zu verwenden, um festzustellen, ob der Agent verfügbar ist: anwesenheitsbasiertes Routing. 


## <a name="configuration"></a>Konfiguration

Die Schritte zum Einrichten einer automatischen Telefonkonferenz und einer Anrufwarteschlange umfassen folgendes unter [Verwalten von Ressourcenkonten:](manage-resource-accounts.md) 

1. Rufen sie eine Dienstnummer ab. 

2. Erwerben Sie eine kostenlose Lizenz für Das Telefonsystem – virtueller Benutzer oder eine kostenpflichtige Telefonsystemlizenz für die Verwendung mit dem Ressourcenkonto oder einer Telefonsystemlizenz.

3. Erstellen Sie das Ressourcenkonto. Eine automatische Telefonzentrale oder Anrufwarteschleife muss über ein zugeordnetes Ressourcenkonto verfügen. 

4. Weisen Sie dem Ressourcenkonto das Telefonsystem oder eine Telefonsystem – virtuelle Benutzerlizenz zu. Weitere Informationen finden Sie unter [Microsoft 365 Phone System – Virtual User license](./teams-add-on-licensing/virtual-user.md).

5. Weisen Sie dem Ressourcenkonto, dem Sie Lizenzen zugewiesen haben, eine Diensttelefonnummer zu. 

6. Erstellen einer Warteschlange oder eine automatische Telefonzentrale für das Telefonsystem 

7. Verknüpfen Sie das Ressourcenkonto mit einer Anrufwarteschleife oder einer automatischen Telefonzentrale. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Websites mit Telefonsystem mit Direct Routing 

Contoso musste die vom lokalen Netzbetreiber bereitgestellte Telefonnummer als Dienstnummer in Office 365 einrichten. 

- Zum Einrichten einer Telefonnummer, die über Direct Routing verfügbar ist, hat Contoso die Anweisungen unter [Verwalten von Ressourcenkonten befolgt.](manage-resource-accounts.md) Da Office 365 die lokalen Telefonnummern nicht kennt, hat Contoso PowerShell zum Abschließen des Setups verwendet.   

- Zum Konfigurieren der automatischen Cloud-Attendant hat Contoso die unter Einrichten einer automatischen [Cloud-Attendant beschriebenen Schritte befolgt.](create-a-phone-system-auto-attendant.md) 

- Zum Einrichten einer Cloudanrufwarteschlange hat Contoso die unter Erstellen einer Cloudanrufwarteschlange [beschriebenen Schritte befolgt.](create-a-phone-system-call-queue.md)  


### <a name="sites-with-phone-system-with-calling-plan"></a>Websites mit Telefonsystem mit Anrufplan

Contoso musste die Telefonnummer portieren, die für Skype for Business Enterprise-VoIP automatische Telefontelefone verwendet wurde, zu Office 365 Phone System. Dadurch konnte dieselbe Nummer als Dienstnummer für die Verwendung als automatische Attendant zugewiesen werden. 

- Zum Portieren der Telefonnummer hat Contoso die Anweisungen unter Übertragen von Telefonnummern an [Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) befolgt und unter Verwalten von Telefonnummern [für Ihre Organisation weitere Anleitungen erhalten.](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Zum Konfigurieren einer automatischen Cloud-Attendant hat Contoso die unter Einrichten einer automatischen [Cloud-Attendant beschriebenen Schritte befolgt.](create-a-phone-system-auto-attendant.md)

-  Zum Einrichten einer Cloudanrufwarteschlange hat Contoso die unter Erstellen einer Cloudanrufwarteschlange [beschriebenen Schritte befolgt.](create-a-phone-system-call-queue.md)  

