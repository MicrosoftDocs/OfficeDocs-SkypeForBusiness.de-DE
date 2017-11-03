---
title: Einrichten des Gastzugriffs auf Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Aktivieren Sie die Funktion für den Gastzugriff in Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7b571d166ed1fdc078ecdb2ecc0f9bfc2ab5cdb3
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
<a name="set-up-guest-access-to-microsoft-teams"></a>Einrichten des Gastzugriffs auf Microsoft Teams
======================================

Microsoft Teams basiert auf Office 365-Gruppen und nutzt außerdem SharePoint Online. Daher müssen bestimmte Einstellungen in Office 365-Gruppen und in SharePoint Online aktiviert werden, um die Funktion für den Gastzugriff in Microsoft Teams zu aktivieren.


## <a name="allow-the-addition-of-guests-in-office-365-groups"></a>Zulassen, dass Gäste hinzugefügt werden in Office 365-Gruppen
<a name="bkmk_ControlAddingGuestUsers"> </a>


1. Melden Sie sich mit Ihrem globalen Office 365-Administrator bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.
    
  
2. Wählen Sie im Navigationsmenü **Einstellungen** und dann **Dienste &amp; Add-Ins** aus.
    
  
3. Wählen Sie **Office 365-Gruppen** aus.
    
     ![Office 365-Gruppen](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. Je nachdem, ob Sie den Zugriff für Team- oder Gruppenbesitzer außerhalb Ihres Unternehmens auf Office 365-Gruppen gewähren möchten, legen Sie die Umschaltfläche auf der Seite „Office 365-Gruppen“ auf **Ein** oder **Aus** fest. Klicken oder tippen Sie neben **Hinzufügen von Personen außerhalb der Organisation zu Gruppen durch Gruppenbesitzer zulassen** auf die Umschaltfläche, um sie in **Ein** zu ändern.


![Dieser Screenshot bildet den Office 365 Groups-Bereich mit den aktivierten Optionen für den Zugriff von Gruppenmitgliedern außerhalb der Organisation auf Gruppeninhalte sowie für das Hinzufügen von Personen außerhalb der Organisation zu Gruppen durch Gruppenbesitzer ab.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
    

## <a name="enable-sharing-in-sharepoint-online"></a>Aktivieren der Freigabe in SharePoint Online

Mit der Freigabeoption in SharePoint Online können Gäste zu Ihrer Organisation hinzugefügt werden. Standardmäßig ist die Freigabeoption aktiviert. Weitere Informationen zur Deaktivierung der Freigabeoption finden Sie unter [Aktivieren oder Deaktivieren der Freigabeoption](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).
  
   Administratoren können Gastkonten in Azure Active Directory unabhängig von den Einstellungen für die externe Freigabe erstellen. Wenn die externe Freigabe deaktiviert ist, können Gastkonten nur von einem Administrator erstellt werden. 
    

> [!IMPORTANT]
> Wenn Sie die Freigabeoption deaktivieren, ist kein Gastzugriff verfügbar. 
  

## <a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>Aktivieren oder deaktivieren des Gastzugriffs auf Microsoft Teams
<a name="bkmk_TurnonOrTurnOff"> </a>

Als Office 365-Administrator müssen Sie die Gastfunktion aktivieren, bevor Sie oder die Benutzer Ihrer Organisation (vor allem Teambesitzer) Gäste hinzufügen können. 

Die Gasteinstellungen werden in Azure Active Directory festgelegt. Es dauert ca. 2 bis 24 Stunden, bis die Änderungen in der gesamten Office 365-Organisation wirksam werden. Wenn Benutzer versuchen, einen Gast zu ihrem Team hinzuzufügen, und dabei die Meldung „Wenden Sie sich an Ihren Administrator“ sehen, ist wahrscheinlich die Gastfunktion nicht aktiviert, oder die Einstellungen sind noch nicht wirksam.



1. Melden Sie sich mit Ihrem globalen Office 365-Administratorkonto bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.
    
  
2. Wählen Sie im Navigationsmenü **Einstellungen** und dann **Dienste &amp; Add-Ins** aus.
    
     ![Melden Sie sich bei Office 365 an, wechseln Sie zum Office 365 Admin Center, wechseln Sie zu „Einstellungen“, und wählen Sie „Dienste &amp; Add-Ins“ aus.](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. Wählen Sie **Microsoft Teams** aus.
    
     ![Screenshot, der die im Office 365 Admin Center ausgewählte Option für das Microsoft Teams-Add-In abbildet.](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. Wählen Sie unter **Zu konfigurierenden Benutzer-/Lizenztyp auswählen** die Option **Gast** aus.
   
    ![Screenshot des Microsoft Teams-Add-Ins, der die ausgewählte Gastlizenz und die aktivierte Microsoft Teams-Option abbildet.](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. Klicken oder tippen Sie auf die Umschaltfläche neben **Microsoft Teams für alle Benutzer dieses Typs aktivieren oder deaktivieren** auf **Ein**, um Teams und Gastzugriff für Ihre Organisation zu aktivieren, und wählen Sie dann **Speichern** aus. 
    
  

