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
localization_priority: Normal
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: 8fa6af4099238f9ab908de2ea8c37340f93c3dff
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494169"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Administratoren: Skype for Business-Einstellungen für einzelne Benutzer konfigurieren

In diesem Artikel wird erläutert, wie Administratoren Skype for Business für eine kleine Anzahl von Benutzern einrichten. Um diese Schritte in Massen durchführen zu können, haben wir Links zu den Windows PowerShell-Cmdlets hinzugefügt, die Sie verwenden können.
  
Informationen darüber, wie Sie zulassen (bzw. blockieren), dass alle Personen in Ihrem Unternehmen mit Personen außerhalb des Unternehmens kommunizieren können, finden Sie unter:
  
- [Zulassen, dass Benutzer externe Skype for Business-Benutzer kontaktieren](allow-users-to-contact-external-skype-for-business-users.md): Sie können Ihrer Organisation erweiterte Skype for Business-Funktionen (Freigeben von Desktops, suchen nach Online-Nutzern usw.) für die Kommunikation mit Personen in einem bestimmten vertrauenswürdigen Unternehmen zur Verfügung stellen. In diesem Artikel wird auch erläutert, wie Sie die Kommunikation mit bestimmten Domänen blockieren.
    
- [Lassen Sie Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md). Sie können zulassen, dass die Benutzer in Ihrer Organisation mit der kostenlosen App Skype for Business andere Skype-Benutzer suchen und mit diesen chatten können.
    
## <a name="configure-general-settings-for-one-user"></a>Konfigurieren von allgemeinen Einstellungen für einen Benutzer
<a name="__toc325019204"> </a>

Sie müssen über [Administratorberechtigungen](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) verfügen, um diese Schritte ausführen zu können.

![Ein Symbol mit dem Skype for Business-](../images/sfb-logo-30x30.png) Logo **im Skype for Business Admin Center**
  
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
|Audio und HD-Video  <br/> |Dieser Person gestatten, audiobesprechungen, Audio-und Videobesprechungen aufzuzeichnen oder keine Besprechungen zu planen (keine).  <br/> |
|Unterhaltungen und Besprechungen aufzeichnen  <br/> |Wählen Sie aus, was diese Person aufzeichnen darf.  <br/> Diese Option steht in Skype for Business Basic nicht zur Verfügung.  <br/> |
|Nicht archivierte Funktionen aus Konformitätsgründen deaktivieren  <br/> | Wählen Sie diese Option aus, wenn Sie rechtlich zur Aufbewahrung elektronisch gespeicherter Informationen verpflichtet sind. <br/>  Wenn Sie diese Option auswählen, werden Features deaktiviert, die nicht erfasst werden, wenn Sie im Exchange Admin Center einen [in-situ-](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) Speicher eingerichtet haben. Die folgenden Features werden deaktiviert: <br/>  Dateiübertragung mittels Chat <br/>  Freigegebene OneNote-Seiten <br/>  PowerPoint-Anmerkungen <br/> |
   
Wenn Sie diese Einstellungen massenhaft konfigurieren möchten, verwenden Sie PowerShell. Weitere Informationen finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="block-external-communications"></a>Sperren der externen Kommunikation
<a name="__toc325019206"> </a>

Nachdem Sie die [Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md) für alle Benutzer in Ihrem Unternehmen aktiviert haben, können Sie unter Ausführung der folgenden Schritte einzelne externe Kommunikationen für bestimmte Benutzer sperren.
  
1. Wählen Sie **Benutzer**aus, wählen Sie die Benutzer aus, deren Einstellungen Sie deaktivieren möchten **** ![, und](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)wählen Sie dann bearbeiten aus.
    
2. Wählen Sie **Externe Kommunikation** aus, und deaktivieren Sie dann die Optionen Ihren Anforderungen entsprechend:
    
   - **Externe Skype for Business-Benutzer**: Deaktivieren Sie dieses Kontrollkästchen, wenn der Benutzer nicht mit Skype for Business-Benutzern in Partnerdomänen kommunizieren soll.
    
   - **Externe Skype-Benutzer**: Deaktivieren Sie dieses Kontrollkästchen, wenn der Benutzer nicht mit Personen kommunizieren soll, die die kostenlose Skype-App verwenden.
    
3. Klicken Sie auf **Speichern**.
    
Wenn Sie diese Einstellungen massenhaft konfigurieren möchten, verwenden Sie PowerShell. Weitere Informationen finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Bearbeiten von Audio-Konferenzeinstellungen für einen Benutzer
<a name="__toc314837483"> </a>

1. Wählen Sie **Benutzer**aus, wählen Sie den Benutzer aus, dessen audiokonferenzeinstellungen Sie bearbeiten möchten, **** ![und wählen](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)Sie dann bearbeiten aus.
    
2. Wählen **** Sie Audiokonferenzen aus, wählen Sie Ihren Audiokonferenz-Anbieter aus, geben Sie die angeforderten Informationen ein, oder ändern Sie Sie, und klicken Sie auf **Speichern**
    
|**Audiokonferenzeinstellung**|**Beschreibung**|
|:-----|:-----|
|**Anbietername** <br/> |Wählen Sie Ihren Anbieter in der Liste aus.  <br/> |
|**Gebührenpflichtige Nummer** (erforderlich) <br/> |Bei einem Drittanbieter-ACP sind diese Telefonnummern diejenigen, die Sie vom Audiokonferenz-Anbieter erhalten haben. Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet, sind dies die Nummern, die für die Audiokonferenz-Brücke festgelegt werden. Formatieren Sie die Zahlen so, wie Sie in Skype for Business-und Microsoft Teams-Besprechungsanfragen angezeigt werden sollen.  <br/> |
|**Gebührenfreien Nummer** <br/> |Bei einem Drittanbieter-ACP sind diese Telefonnummern diejenigen, die Sie vom Audiokonferenz-Anbieter erhalten haben. Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet, sind dies die Nummern, die für die Audiokonferenz-Brücke festgelegt werden. Formatieren Sie die Zahlen so, wie Sie in Skype for Business-und Microsoft Teams-Besprechungsanfragen angezeigt werden sollen.  <br/> |
|**Konferenz-ID und PIN** erforderlich <br/> |Die Teilnehmer-PIN oder der konferenzcode, der für die Teilnahme an Besprechungen verwendet wird, die von diesem Benutzer geplant werden und von einem Drittanbieter für Audiokonferenzen bereitgestellt werden. Wenn der Benutzer Microsoft als Audiokonferenz-Anbieter verwendet, ist dies nicht erforderlich.  <br/> |
   
Wenn Sie diese Einstellungen massenhaft konfigurieren möchten, verwenden Sie PowerShell. Weitere Informationen finden Sie unter [Einrichten der Telefonnummern in Einladungen](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Einrichten Ihres Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Verwandte Themen 

[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
