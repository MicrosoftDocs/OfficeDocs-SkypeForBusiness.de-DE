---
title: Administratoren Skype for Business-Einstellungen für einzelne Benutzer konfigurieren
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
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
ms.openlocfilehash: f99c99fc291a2df71a3e47448e3cc8fcf01e371f
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370915"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Administratoren: Skype for Business-Einstellungen für einzelne Benutzer konfigurieren

In diesem Artikel wird erläutert, wie Administratoren Skype for Business für eine kleine Anzahl von Benutzern einrichten. Klicken Sie dazu diese Schritte in einer Sammeloperation haben wir Links zu Windows PowerShell-Cmdlets enthalten, die Sie verwenden können.
  
Informationen darüber, wie Sie zulassen (bzw. blockieren), dass alle Personen in Ihrem Unternehmen mit Personen außerhalb des Unternehmens kommunizieren können, finden Sie unter:
  
- [Wenden Sie sich an externe Skype für Unternehmensbenutzer durch Benutzer zulassen](allow-users-to-contact-external-skype-for-business-users.md): Sie können Ihrer Organisation verwenden können erweiterte Skype für Business-Features (Desktops freigeben, suchen Sie nach, wer online, usw. ist) kommunizieren mit Personen in einem bestimmten vertrauenswürdigen (verbundgeschäftspartner). Der Artikel wird auch die Kommunikation mit bestimmten Domänen blockieren erläutert.
    
- [Lassen Sie Skype für Unternehmensbenutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md). Sie können zulassen, dass die Benutzer in Ihrer Organisation mit der kostenlosen App Skype for Business andere Skype-Benutzer suchen und mit diesen chatten können.
    
## <a name="configure-general-settings-for-one-user"></a>Konfigurieren von allgemeinen Einstellungen für einen Benutzer
<a name="__toc325019204"> </a>

Sie benötigen [Administratorberechtigungen](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , um diese Schritte auszuführen.

![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**
  
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
|Unterhaltungen und Besprechungen aufzeichnen  <br/> |Wählen Sie aus, was diese Person aufzeichnen darf.  <br/> Diese Option ist nicht mit Skype für Business Basic verfügbar.  <br/> |
|Nicht archivierte Funktionen aus Konformitätsgründen deaktivieren  <br/> | Wählen Sie diese Option aus, wenn Sie rechtlich zur Aufbewahrung elektronisch gespeicherter Informationen verpflichtet sind. <br/>  Durch Auswählen dieser Option wird deaktiviert Features, die erfasst werden nicht, wenn Sie eine [Compliance-Archiv](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) im Exchange Administrationscenter in eingerichtet haben. Die folgenden Features werden deaktiviert: <br/>  Dateiübertragung mittels Chat <br/>  Freigegebene OneNote-Seiten <br/>  PowerPoint-Anmerkungen <br/> |
   
Um diese Einstellung als Massenbearbeitung zu konfigurieren, verwenden Sie PowerShell. Weitere Informationen finden Sie unter [Verwalten von Richtlinien in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).
  
## <a name="block-external-communications"></a>Sperren der externen Kommunikation
<a name="__toc325019206"> </a>

Nachdem Sie die [Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md) für alle Benutzer in Ihrem Unternehmen aktiviert haben, können Sie unter Ausführung der folgenden Schritte einzelne externe Kommunikationen für bestimmte Benutzer sperren.
  
1. Wählen Sie **Benutzer**, wählen Sie die Benutzer, dessen Einstellungen Sie deaktivieren möchten, und wählen Sie dann auf **Bearbeiten** ![bearbeiten](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Wählen Sie **Externe Kommunikation** aus, und deaktivieren Sie dann die Optionen Ihren Anforderungen entsprechend:
    
   - **Externe Skype for Business-Benutzer**: Deaktivieren Sie dieses Kontrollkästchen, wenn der Benutzer nicht mit Skype for Business-Benutzern in Partnerdomänen kommunizieren soll.
    
   - **Externe Skype-Benutzer**: Deaktivieren Sie dieses Kontrollkästchen, wenn der Benutzer nicht mit Personen kommunizieren soll, die die kostenlose Skype-App verwenden.
    
3. Klicken Sie auf **Speichern**.
    
Um diese Einstellung als Massenbearbeitung zu konfigurieren, verwenden Sie PowerShell. Weitere Informationen finden Sie unter [Verwalten von Kommunikationen in Skype for Business Online mit externen Benutzern und Organisationen](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Bearbeiten von Audiokonferenzen-Einstellungen für einen Benutzer
<a name="__toc314837483"> </a>

1. Wählen Sie **Benutzer**aus, wählen Sie den Benutzer, dessen Sie um zu bearbeiten, WAN-Audiokonferenzen Einstellungen, und wählen Sie dann auf **Bearbeiten** ![bearbeiten](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Wählen Sie **Audiokonferenzen**, wählen Sie Ihren Audiokonferenz-Anbieter, geben Sie oder ändern Sie die angeforderte Informationen, und klicken Sie dann auf **Speichern**.
    
|**Audiokonferenzeinstellung**|**Beschreibung**|
|:-----|:-----|
|**Name des Anbieters** <br/> |Wählen Sie aus der Liste der Anbieter.  <br/> |
|**Gebührenpflichtige Nummer** (erforderlich) <br/> |Für ein Drittanbieter-ACP sind diese Rufnummern diejenigen aus, die Sie vom Anbieter von Audiokonferenzen erhalten haben. Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet, sind dies die Nummern, die für die Audiokonferenz-Brücke festgelegt werden. Formatieren Sie die Zahlen in Skype für Geschäfts- und Microsoft-Teams, Besprechungsanfragen angezeigt werden soll.  <br/> |
|**Gebührenfreien Nummer** <br/> |Für ein Drittanbieter-ACP sind diese Rufnummern diejenigen aus, die Sie vom Anbieter von Audiokonferenzen erhalten haben. Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet, sind dies die Nummern, die für die Audiokonferenz-Brücke festgelegt werden. Formatieren Sie die Zahlen in Skype für Geschäfts- und Microsoft-Teams, Besprechungsanfragen angezeigt werden soll.  <br/> |
|**Konferenz-ID und PIN-Nummer** (erforderlich) <br/> |Die Teilnehmer PIN oder Konferenz Code verwendet, um an Besprechungen teilnehmen, die von diesem Benutzer geplant werden und werden von einem Drittanbieter-Audiokonferenz-Anbieter bereitgestellt. Wenn der Benutzer Microsoft als Audiokonferenz-Anbieter verwendet, wird nicht erforderlich sein.  <br/> |
   
Verwenden Sie zum Konfigurieren dieser Einstellungen in einer Sammeloperation PowerShell. Finden Sie unter [Einrichten des Telefons, Zahlen auf enthalten lädt](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Verwandte Themen 

[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 