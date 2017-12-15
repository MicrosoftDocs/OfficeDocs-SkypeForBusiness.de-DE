---
title: "Administratoren Skype for Business-Einstellungen für einzelne Benutzer konfigurieren"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836

description: "Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. "
---

# Administratoren: Skype for Business-Einstellungen für einzelne Benutzer konfigurieren

In diesem Artikel wird erläutert, wie Administratoren Skype for Business für eine kleine Anzahl von Benutzern einrichten. Damit Sie diese Schritte als Massenvorgang ausführen können, sind Links zu den Windows PowerShell-Cmdlets enthalten, die Sie verwenden können.
  
Informationen darüber, wie Sie zulassen (bzw. blockieren), dass alle Personen in Ihrem Unternehmen mit Personen außerhalb des Unternehmens kommunizieren können, finden Sie unter:
  
- [Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren](allow-users-to-contact-external-skype-for-business-users.md) : Sie können zulassen, dass die Personen in Ihrer Organisation erweiterte Skype for Business-Funktionen (Desktops freigeben, Personen suchen, die online sind) verwenden, um mit Personen in einem bestimmten vertrauenswürdigen Unternehmen (Partnerunternehmen) zu kommunizieren. Es wird auch erläutert, wie Kommunikationen mit bestimmten Domänen blockiert werden können.
    
- [Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md) . Sie können zulassen, dass die Benutzer in Ihrer Organisation mit der kostenlosen App Skype for Business andere Skype-Benutzer suchen und mit diesen chatten können.
    
## Konfigurieren von allgemeinen Einstellungen für einen Benutzer
<a name="__toc325019204"> </a>

Sie müssen über [Informationen zu Administratorrollen von Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) verfügen, um diese Schritte auszuführen.
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wählen Sie **Admin Center** > **Skype for Business** aus.
    
3. Wählen Sie **Benutzer** aus.
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Wählen Sie aus, welche Benutzer Sie bearbeiten möchten. 
    
5. Wählen Sie im rechten Bereich **Bearbeiten** aus.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Aktivieren oder deaktivieren Sie auf der Optionsseite **Allgemein** die Kontrollkästchen neben den Funktionen, die Sie ändern möchten, und wählen Sie dann **Speichern** aus.
    
|**Option**|**Details**|
|:-----|:-----|
|Audio und HD-Video  <br/> |Zulassen, dass diese Person Audiobesprechungen bzw. Audio- und Videobesprechungen aufzeichnen kann, oder die Planung von Besprechungen für keinen Benutzer zulassen (Keiner).  <br/> |
|Unterhaltungen und Besprechungen aufzeichnen  <br/> |Wählen Sie aus, was diese Person aufzeichnen darf.  <br/> Diese Option ist für Skype for Business Basic nicht verfügbar.  <br/> |
|Nicht archivierte Funktionen aus Konformitätsgründen deaktivieren  <br/> | Wählen Sie diese Option aus, wenn Sie rechtlich zur Aufbewahrung elektronisch gespeicherter Informationen verpflichtet sind. <br/>  Durch die Auswahl dieser Option werden Funktionen deaktiviert, die nicht erfasst werden, wenn im Exchange Admin Center ein[In-Situ-Speicher](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) eingerichtet ist. Die folgenden Funktionen werden deaktiviert: <br/>  Dateiübertragung mittels Chat <br/>  Freigegebene OneNote-Seiten <br/>  PowerPoint-Anmerkungen <br/> |
   
Um diese Einstellung als Massenvorgang zu konfigurieren, verwenden Sie PowerShell. Weitere Informationen finden Sie unter [Verwalten von Richtlinien in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).
  
## Sperren der externen Kommunikation
<a name="__toc325019206"> </a>

Nachdem Sie die [Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md) für alle Benutzer in Ihrem Unternehmen aktiviert haben, können Sie unter Ausführung der folgenden Schritte einzelne externe Kommunikationen für bestimmte Benutzer sperren.
  
1. Klicken Sie auf **Benutzer**, wählen Sie die Benutzer aus, für die Sie die Einstellungen deaktivieren möchten, und klicken Sie dann auf **Bearbeiten**![Bearbeiten](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Wählen Sie **Externe Kommunikation** aus, und deaktivieren Sie dann die Optionen Ihren Anforderungen entsprechend:
    
  - **Externe Skype for Business-Benutzer**: Deaktivieren Sie dieses Kontrollkästchen, wenn es dem Benutzer nicht möglich sein soll, mit Skype for Business-Benutzern in Partnerdomänen zu kommunizieren.
    
  - **Externe Skype-Benutzer**: Deaktivieren Sie dieses Kontrollkästchen, wenn es dem Benutzer nicht möglich sein soll, mit Personen zu kommunizieren, die die kostenlose Skype-App verwenden.
    
3. Klicken Sie auf **Speichern**.
    
Um diese Einstellung als Massenbearbeitung zu konfigurieren, verwenden Sie PowerShell. Weitere Informationen finden Sie unter [Verwalten von Kommunikationen in Skype for Business Online mit externen Benutzern und Organisationen](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).
  
## Bearbeiten von Audiokonferenzeinstellungen für einen Benutzer
<a name="__toc314837483"> </a>

1. Wählen Sie **Benutzer** aus, wählen Sie den Benutzer aus, dessen Audiokonferenzeinstellungen Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten**![Bearbeiten](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) aus.
    
2. Wählen Sie **Audiokonferenz** aus, wählen Sie Ihren Audiokonferenzanbieter aus, geben Sie die erforderlichen Informationen ein, oder ändern Sie sie, und klicken Sie dann auf **Speichern**.
    
|**Audiokonferenzeinstellung**|**Beschreibung**|
|:-----|:-----|
|**Anbietername** <br/> |Wählen Sie Ihren Anbieter aus der Liste aus.  <br/> |
|**Gebührenpflichtige Nummer** (erforderlich) <br/> |Bei einem Drittanbieter-ACP handelt es sich um die Telefonnummern, die Sie vom Audiokonferenzanbieter erhalten haben. Wenn der Benutzer Microsoft als Audiokonferenzanbieter nutzt, werden diese Nummern in der Audiokonferenzbrücke festgelegt. Formatieren Sie die Nummern so, wie sie in Skype for Business und in Microsoft Teams-Besprechungsanfragen angezeigt werden sollen.  <br/> |
|**Gebührenfreie Nummer** <br/> |Bei einem Drittanbieter-ACP handelt es sich um die Telefonnummern, die Sie vom Audiokonferenzanbieter erhalten haben. Wenn der Benutzer Microsoft als Audiokonferenzanbieter nutzt, werden diese Nummern in der Audiokonferenzbrücke festgelegt. Formatieren Sie die Nummern so, wie sie in Skype for Business und in Microsoft Teams-Besprechungsanfragen angezeigt werden sollen.  <br/> |
|**Conference ID and PIN** (Konferenzkennung und PIN) (erforderlich) <br/> |Die Teilnehmer-PIN (oder der Konferenzcode), die für die Teilnahme an Besprechungen verwendet wird, die von diesem Benutzer geplant und von einem Drittanbieter für Audiokonferenzen bereitgestellt werden. Wenn der Benutzer Microsoft als Audiokonferenzanbieter nutzt, ist dies nicht erforderlich.  <br/> |
   
Um diese Einstellung als Massenvorgang zu konfigurieren, verwenden Sie PowerShell. Weitere Informationen finden Sie unter [Festlegen der in Einladungen enthaltenen Audiokonferenz-Telefonnummern für Besprechungsorganisatoren](../audio-conferencing-in-office-365/set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
## 
<a name="__toc314837483"> </a>

||
|:-----|
|![Symbol für LinkedIn Learning](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Neu bei Office 365?**         Entdecken Sie kostenlose Videokurse für **Office 365-Administratoren und IT-Experten**, bereitgestellt von LinkedIn Learning. |
   
## Verwandte Themen
<a name="__toc314837483"> </a>

[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)[Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  

