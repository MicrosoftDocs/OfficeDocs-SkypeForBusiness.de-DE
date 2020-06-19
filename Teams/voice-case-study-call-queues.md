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
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786022"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso-Fallstudie: automatische Telefonzentralen und Anrufwarteschlangen

Contoso war mit automatischen Telefonzentralen und Anrufwarteschlangen aus der lokalen Skype for Business-Bereitstellung vertraut. Wenn Sie wissen möchten, wie die automatischen Cloud-Telefonzentralen eingerichtet [werden](what-are-phone-system-auto-attendants.md) , haben Sie die automatische automatische Telefonzentrale in der Cloud überprüft. Beispiel für ein [kleines Unternehmen – Einrichten einer automatischen Telefon](tutorial-org-aa.yml)zentrale. Wenn Sie mehr über die verfügbaren Optionen zum Einrichten von Anrufwarteschlangen erfahren möchten, hat Contoso [eine Cloud-Anrufwarteschlange erstellt](create-a-phone-system-call-queue.md).  

## <a name="requirements-depending-on-site-type"></a>Anforderungen je nach Art der Website

Je nach Typ der Website hatte Contoso die folgenden Anforderungen:

- Websitetyp A: herkömmliche Legacy-Telefoniesysteme 

  Websitetyp A erforderlich, um die gleiche Telefonnummer, die der Rezeption zugeordnet ist, als Nummer für Ihre automatischen Telefonzentralen beizubehalten. Die wichtigsten Abteilungen für jede dieser Websites hätten eigene Anrufwarteschlangen, die an Teammitglieder weitergeleitet werden. Es gab eine Mischung von Websites, die das Telefonsystem mit direktem Routing und Telefonsystem mit Anrufplänen verwendeten.  

- Website Typ B: Skype for Business Enterprise-VoIP 

  Der Websitetyp B hatte vorhandene automatische Telefonzentralen und Anrufwarteschlangen, die für die Migration zu Teams benötigt wurden. Contoso musste die Telefonnummern beibehalten, die den automatischen Telefonzentralen zugeordnet sind. Contoso hat die Mehrheit dieser Websites mit Anrufplänen in das Telefon System verschoben. In den wenigen Speicherorten, an denen keine Anrufpläne verfügbar waren, hat Contoso diese Websites jedoch in eine direkte Routing Konfiguration verschoben.  

- Websitetyp C: Skype for Business Enterprise Voice & herkömmliches Legacy-Telefonsystem 

  Der Websitetyp C hatte vorhandene automatische Telefonzentralen, die sich im traditionellen Legacy-Telefoniesystem befanden. Die Entscheidungen und Konfigurationen für diese Website waren mit dem Websitetyp A identisch.   

- Für alle Websitetypen stellte Contoso die folgenden Fragen:

  - F: werden neue oder bestehende Nummern verwendet? 
    A: contoso hat entschieden, vorhandene Telefonnummern für die Zuweisung zum Dienstkonto für die automatische Telefonzentrale zu verwenden. 

  - F: Wann wird die automatische Telefonzentrale für eingehende Anrufe zur Verfügung stehen? 
    A: contoso hat entschieden, Geschäftszeiten festzulegen und Anrufe, die nach Geschäftszeiten empfangen werden, an die automatische Telefonzentrale "After Hours" weitergeleitet.  

  - F: wie werden die Anrufe an Mitglieder in einer Anrufwarteschlange weitergeleitet: Attendant, seriell oder Round Robin-Routing? 
    A: contoso hat beschlossen, Attendant-Routing zu verwenden. 

  - Frage: wie können wir feststellen, wann ein Nutzer einen Anruf entgegenbringen sollte oder nicht? 
    A: contoso hat entschieden, die Anruf Behandlungsoptionen zu verwenden, um festzustellen, ob der Agent verfügbar ist: Anwesenheits basiertes Routing. 


## <a name="configuration"></a>Konfiguration

Die Schritte zum Einrichten einer automatischen Telefonzentrale und einer Anrufwarteschlange beinhalten die folgenden Gliederungen unter [Verwalten von Ressourcenkonten](manage-resource-accounts.md): 

1. Rufen sie eine Dienstnummer ab. 

2. Besorgen Sie sich ein kostenloses Telefonsystem – eine virtuelle Benutzerlizenz oder eine gebührenpflichtige Telefonsystem Lizenz, die Sie mit dem Ressourcenkonto oder einer Telefonsystem Lizenz verwenden können.

3. Erstellen Sie das Ressourcenkonto. Eine automatische Telefonzentrale oder Anrufwarteschleife muss über ein zugeordnetes Ressourcenkonto verfügen. 

4. Weisen Sie dem Ressourcenkonto das Telefonsystem oder eine Telefonsystem – virtuelle Benutzerlizenz zu. Weitere Informationen finden Sie unter [Microsoft 365 Phone System – Virtual User License](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).

5. Weisen Sie dem Ressourcenkonto, dem Sie Lizenzen zugewiesen haben, eine Dienst Telefonnummer zu. 

6. Erstellen einer Warteschlange oder eine automatische Telefonzentrale für das Telefonsystem 

7. Verknüpfen Sie das Ressourcenkonto mit einer Anrufwarteschleife oder einer automatischen Telefonzentrale. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Websites mit Telefon System mit direktem Routing 

Contoso musste die Telefonnummer, die vom lokalen Netzbetreiber bereitgestellt wurde, als Dienstnummer in Office 365 einrichten. 

- Um eine Telefonnummer einzurichten, die über Direct Routing zur Verfügung steht, folgte Contoso den Anweisungen unter [Verwalten von Ressourcenkonten](manage-resource-accounts.md). Da Office 365 die lokalen Telefonnummern nicht kennt, hat Contoso PowerShell verwendet, um das Setup abzuschließen.   

- Zum Konfigurieren der automatischen Cloud-Telefonzentrale befolgte Contoso die in [Einrichten einer automatischen Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md)erläuterten Schritte. 

- Zum Einrichten einer Cloud-Anrufwarteschlange folgte Contoso den Schritten unter [Erstellen einer Cloud-Anrufwarteschlange](create-a-phone-system-call-queue.md).  


### <a name="sites-with-phone-system-with-calling-plan"></a>Websites mit Telefon System mit Anrufplan

Contoso musste die Telefonnummer, die für Skype for Business Enterprise-VoIP-Telefonzentralen verwendet wurde, an das Office 365 Phone-System portieren. Dadurch konnte dieselbe Nummer als Dienstnummer für die Verwendung als automatische Telefonzentrale zugewiesen werden. 

- Um die Telefonnummer zu portieren, folgte Contoso den Anweisungen unter [übertragen von Telefonnummern in Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) und erhielt zusätzliche Anleitungen unter [Verwalten von Telefonnummern für Ihre Organisation](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

- Zum Konfigurieren einer automatischen Cloud-Telefonzentrale befolgte Contoso die in [Einrichten einer automatischen Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md)erläuterten Schritte.

-  Zum Einrichten einer Cloud-Anrufwarteschlange folgte Contoso den Schritten unter [Erstellen einer Cloud-Anrufwarteschlange](create-a-phone-system-call-queue.md).  

 