---
title: "Aufrufen der Pläne bekannte Probleme"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0

description: "Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. "
---

# Aufrufen der Pläne bekannte Probleme

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den [Haftungsausschluss](baa3645a-0518-472e-942e-971c63ba4ca0.md#MT_Footer).  
  
Calling Plans in Office 365 are a new feature found in Skype for Business Online. There are current issues that are being tracked, actively investigated and will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online and are listed below.
  
## Bekannte Probleme bei Festnetzanrufen

|**Bekanntes Problem**|**Anmerkungen**|
|:-----|:-----|
|Durch Überwechseln von Lizenzen für die technische Vorschau zu Produktionslizenzen für Festnetzanrufe wird die Lizenz nicht automatisch aktualisiert.  <br/> |Purchase your new licenses first so they are ready to be assigned to your users. Remove the promo (Tech Preview) license from a user and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **International Calling Plan** licenses to the user. <br/> Falls Sie Lizenzen für mehrere Benutzer entfernen und hinzufügen, ist es äußerst wichtig, dass Sie zunächst mithilfe von Windows PowerShell die Lizenzen aller Benutzer entfernen und dann **UNMITTELBAR** danach ebenfalls mit Windows PowerShell die Lizenzen für alle Benutzer zuweisen. Damit stellen Sie sicher, dass es nicht zu einer Dienstunterbrechung kommt, wenn Sie große Mengen von Benutzerlizenzen zuweisen. Beispiele für PowerShell-Skripts finden Sie unter[Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> > [!CAUTION]> If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license. You should **NOT** also assign a voice calling plan.> However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** and/or **International Calling Plan** license for those users. See[Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).           |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  
## Siehe auch
<a name="MT_Footer"> </a>

#### Weitere Ressourcen

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)
  
[Audio-Konferenzen Grußformeln durchführen Periode](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)

