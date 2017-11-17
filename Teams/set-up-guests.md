---
title: Aktivieren oder deaktivieren des Gastzugriffs auf Microsoft Teams
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
description: "Aktivieren oder Deaktivieren der Funktion für den Gastzugriff in Microsoft Teams"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: a996f7cc9154d04870e4dea00da950d340de16e2
ms.sourcegitcommit: 4a396557d51c7fb246144cd682bcf5e6a2c823be
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2017
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>Aktivieren oder deaktivieren des Gastzugriffs auf Microsoft Teams
======================================





  



Als Office 365-Administrator müssen Sie die Gastfunktion aktivieren, bevor Sie oder die Benutzer Ihrer Organisation (vor allem Teambesitzer) Gäste hinzufügen können. 

Die Gasteinstellungen werden in Azure Active Directory festgelegt. Es dauert ca. 2 bis 24 Stunden, bis die Änderungen in der gesamten Office 365-Organisation wirksam werden. Wenn Benutzer versuchen, einen Gast zu ihrem Team hinzuzufügen, und dabei die Meldung „Wenden Sie sich an Ihren Administrator“ sehen, ist wahrscheinlich die Gastfunktion nicht aktiviert, oder die Einstellungen sind noch nicht wirksam.


> [!IMPORTANT]
> Um die Nutzung der Gastzugriffsfunktion in vollem Umfang zu ermöglichen, müssen Sie die gegenseitige Abhängigkeit bezüglich der Kernautorisierung von Microsoft Teams, Azure Active Directory und Office 365 verstehen. Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).

1. Melden Sie sich mit Ihrem globalen Office 365-Administratorkonto bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.
    
  
2. Wählen Sie im Navigationsmenü **Einstellungen** und dann **Dienste &amp; Add-Ins** aus.
    
     ![Melden Sie sich bei Office 365 an, wechseln Sie zum Office 365 Admin Center, wechseln Sie zu „Einstellungen“, und wählen Sie „Dienste &amp; Add-Ins“ aus.](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. Wählen Sie **Microsoft Teams** aus.
    
     ![Screenshot, der die im Office 365 Admin Center ausgewählte Option für das Microsoft Teams-Add-In abbildet.](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. Wählen Sie unter **Zu konfigurierenden Benutzer-/Lizenztyp auswählen** die Option **Gast** aus.
   
    ![Screenshot des Microsoft Teams-Add-Ins, der die ausgewählte Gastlizenz und die aktivierte Microsoft Teams-Option abbildet.](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. Klicken oder tippen Sie auf die Umschaltfläche neben **Microsoft Teams für alle Benutzer dieses Typs aktivieren oder deaktivieren** auf **Ein**, um Teams und Gastzugriff für Ihre Organisation zu aktivieren, und wählen Sie dann **Speichern** aus. 
    
  

