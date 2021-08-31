---
title: Administratoren Skype for Business-Einstellungen für einzelne Benutzer konfigurieren
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: 'Erfahren Sie, wie Skype for Business Einstellungen für einzelne Benutzer ändern können, z. B.: Audio- und Videokonferenzen, Aufzeichnen von Anrufen und Besprechungen. '
ms.openlocfilehash: e96e33f5a83030f187c6e6c3caaee197c2d81a2f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731824"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Administratoren: Skype for Business-Einstellungen für einzelne Benutzer konfigurieren

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> Das Microsoft Teams Admin Center wurde durch Skype for Business Admin Center (Legacyportal) ersetzt. Alle Einstellungen für die Skype for Business befinden sich jetzt im Teams Admin Center. Ihnen muss die [Azure AD-Administratorrolle](/azure/active-directory/roles/permissions-reference) eines globalen Administrator oder Skype for Business zugewiesen sein, damit Skype for Business Features im Teams Admin Center verwalten können. Weitere Informationen finden Sie unter [Verwalten Skype for Business-Einstellungen im Microsoft Teams Admin Center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).

In diesem Artikel wird erläutert, wie Administratoren Skype for Business für eine kleine Anzahl von Benutzern einrichten. Um diese Schritte in Massen zu unternehmen, haben wir Links zu den cmdlets Windows PowerShell, die Sie verwenden können, aufgenommen.
  
Informationen darüber, wie Sie zulassen (bzw. blockieren), dass alle Personen in Ihrem Unternehmen mit Personen außerhalb des Unternehmens kommunizieren können, finden Sie unter:
  
- Zulassen, dass Benutzer externe [Skype for Business-Benutzer](allow-users-to-contact-external-skype-for-business-users.md)kontaktieren: Sie können zulassen, dass in Ihrer Organisation erweiterte Skype for Business-Features (Desktops freigeben, nach Onlinebenutzern suchen usw.) verwendet werden, um mit Personen in einem bestimmten vertrauenswürdigen Unternehmen (Partnerunternehmen) zu kommunizieren. In diesem Artikel wird auch erläutert, wie Sie die Kommunikation mit bestimmten Domänen blockieren.
    
- [Ermöglichen Skype for Business, dass Benutzer Skype Hinzufügen von Kontakten hinzufügen.](let-skype-for-business-users-add-skype-contacts.md) Sie können zulassen, dass die Benutzer in Ihrer Organisation mit der kostenlosen App Skype for Business andere Skype-Benutzer suchen und mit diesen chatten können.
    
## <a name="configure-general-settings-for-one-user"></a>Konfigurieren von allgemeinen Einstellungen für einen Benutzer
<a name="__toc325019204"> </a>

Sie müssen über [Administratorberechtigungen verfügen,](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) um diese Schritte ausführen zu können.

![Ein Symbol mit dem Skype for Business Logo.](../images/sfb-logo-30x30.png) **Verwenden des Skype for Business Admin Centers**
  
1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.
    
2. Wählen Sie **Admin Center** > **Skype for Business** aus.
    
3. Wählen Sie **Benutzer** aus.
    
    ![Wählen Sie im Skype for Business Admin Centerdie Option Benutzer aus.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Wählen Sie aus, welche Benutzer Sie bearbeiten möchten.
    
5. Wählen Sie im rechten Bereich **Bearbeiten** aus.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Aktivieren oder deaktivieren Sie auf der Optionsseite **Allgemein** die Kontrollkästchen neben den Funktionen, die Sie ändern möchten, und wählen Sie dann **Speichern** aus.
    
|**Option**|**Details**|
|:-----|:-----|
|Audio und HD-Video  <br/> |Lassen Sie zu, dass diese Person Audiobesprechungen, Audio- und Videobesprechungen auf protokollieren kann, oder lassen Sie nicht zu, dass sie Besprechungen (keine) plant.  <br/> |
|Unterhaltungen und Besprechungen aufzeichnen  <br/> |Wählen Sie aus, was diese Person aufzeichnen darf.  <br/> Diese Option ist in Skype for Business Basic nicht verfügbar.  <br/> |
|Nicht archivierte Funktionen aus Konformitätsgründen deaktivieren  <br/> | Wählen Sie diese Option aus, wenn Sie rechtlich zur Aufbewahrung elektronisch gespeicherter Informationen verpflichtet sind. <br/>  Wenn Sie diese Option auswählen, werden Features deaktiviert, die nicht erfasst werden, wenn Sie im Exchange Admin Center einen [In-Exchange](/exchange/security-and-compliance/in-place-and-litigation-holds) eingerichtet haben. Die folgenden Features werden deaktiviert: <br/>  Dateiübertragung mittels Chat <br/>  Freigegebene OneNote-Seiten <br/>  PowerPoint-Anmerkungen <br/> |
   
Wenn Sie diese Einstellungen als Massen konfigurieren möchten, verwenden Sie PowerShell. Weitere [Informationen finden Sie unter Einrichten des Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="block-external-communications"></a>Sperren der externen Kommunikation
<a name="__toc325019206"> </a>

Nachdem Sie die [Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md) für alle Benutzer in Ihrem Unternehmen aktiviert haben, können Sie unter Ausführung der folgenden Schritte einzelne externe Kommunikationen für bestimmte Benutzer sperren.
  
1. Wählen **Sie Benutzer** aus, wählen Sie die Benutzer aus, deren Einstellungen Sie deaktivieren möchten, und wählen Sie dann **Bearbeiten** ![ Bearbeiten aus. ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)
    
2. Wählen Sie **Externe Kommunikation** aus, und deaktivieren Sie dann die Optionen Ihren Anforderungen entsprechend:
    
   - **Externe Skype for Business-Benutzer**: Deaktivieren Sie dieses Kontrollkästchen, wenn der Benutzer nicht mit Skype for Business-Benutzern in Partnerdomänen kommunizieren soll.
    
   - **Externe Skype-Benutzer**: Deaktivieren Sie dieses Kontrollkästchen, wenn der Benutzer nicht mit Personen kommunizieren soll, die die kostenlose Skype-App verwenden.
    
3. Klicken Sie auf **Speichern**.
    
Wenn Sie diese Einstellungen als Massen konfigurieren möchten, verwenden Sie PowerShell. Weitere [Informationen finden Sie unter Einrichten des Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Bearbeiten der Audiokonferenzeinstellungen für einen Benutzer
<a name="__toc314837483"> </a>

1. Wählen **Sie Benutzer** aus, wählen Sie den Benutzer aus, dessen Audiokonferenzeinstellungen Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten.** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)
    
2. Wählen **Sie Audiokonferenzen aus,** wählen Sie Ihren Audiokonferenzanbieter aus, geben Sie die angeforderten Informationen ein, oder ändern Sie sie, und klicken Sie dann auf **Speichern.**
    
|**Audiokonferenzeinstellung**|**Beschreibung**|
|:-----|:-----|
|**Anbietername** <br/> |Wählen Sie Ihren Anbieter aus der Liste aus.  <br/> |
|**Gebührenpflichtige Nummer** (erforderlich) <br/> |Bei einem Drittanbieter-ACP handelt es sich bei diesen Telefonnummern um die Telefonnummern, die Sie vom Audiokonferenzanbieter erhalten haben. Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet, sind dies die Nummern, die für die Audiokonferenz-Brücke festgelegt werden. Formatieren Sie die Nummern so, wie sie in Besprechungsanfragen Skype for Business und Microsoft Teams sollen.  <br/> |
|**Gebührenfreien Nummer** <br/> |Bei einem Drittanbieter-ACP handelt es sich bei diesen Telefonnummern um die Telefonnummern, die Sie vom Audiokonferenzanbieter erhalten haben. Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet, sind dies die Nummern, die für die Audiokonferenz-Brücke festgelegt werden. Formatieren Sie die Nummern so, wie sie in Besprechungsanfragen Skype for Business und Microsoft Teams sollen.  <br/> |
|**Konferenz-ID und PIN** (erforderlich) <br/> |Die Teilnehmer-PIN oder der Konferenzcode, die für die Teilnahme an Besprechungen verwendet wird, die von diesem Benutzer geplant und von einem Drittanbieter für Audiokonferenzen bereitgestellt werden. Wenn der Benutzer Microsoft als Audiokonferenzanbieter verwendet, ist dies nicht erforderlich.  <br/> |
   
Wenn Sie diese Einstellungen als Massen konfigurieren möchten, verwenden Sie PowerShell. Siehe [Festlegen der in Einladungen](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) enthaltenen Telefonnummern Einrichten Ihres Computers für [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Verwandte Themen 

[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
