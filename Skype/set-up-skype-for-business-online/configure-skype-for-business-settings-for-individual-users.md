---
title: "Administratoren konfigurieren Skype für Business-Einstellungen für einzelne Benutzer"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: "Erfahren Sie, wie die Skype für Business-Einstellungen für einzelne Benutzer zu ändern, wie: Audio-und Videokonferenzen, Aufzeichnung von Anrufen und Besprechungen. "
ms.openlocfilehash: 0623c6dd913316584bd38e4076317c050c4a2812
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Administratoren: Konfigurieren von Skype für die Business-Einstellungen für einzelne Benutzer

In diesem Artikel wird erläutert, wie Administratoren Skype für Unternehmen für eine kleine Anzahl von Benutzern konfigurieren. Klicken Sie dazu diese Schritte in einer Sammeloperation haben wir Links zu Windows PowerShell-Cmdlets enthalten, die Sie verwenden können.
  
Wenn Sie zulassen (oder blockieren) alle Personen in Ihrem Unternehmen mit externen Personen kommunizieren, finden Sie unter:
  
- [Wenden Sie sich an externe Skype für Unternehmensbenutzer durch Benutzer zulassen](allow-users-to-contact-external-skype-for-business-users.md): Sie können Ihrer Organisation verwenden können erweiterte Skype für Business-Features (Desktops freigeben, suchen Sie nach, wer online, usw. ist) kommunizieren mit Personen in einem bestimmten vertrauenswürdigen (verbundgeschäftspartner). Der Artikel wird auch die Kommunikation mit bestimmten Domänen blockieren erläutert.
    
- [Lassen Sie Skype für Unternehmensbenutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md). Sie können Ihrer Organisation verwenden Skype für Unternehmen zu suchenden und Instant Messaging-Personen, die Skype, kostenlose app verwenden können.
    
## <a name="configure-general-settings-for-one-user"></a>Konfigurieren der allgemeinen Einstellungen für einen Benutzer
<a name="__toc325019204"> </a>

Sie benötigen [Administratorberechtigungen](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , um diese Schritte auszuführen.
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wählen Sie **Admin Center** > **Skype for Business** aus.
    
3. Wählen Sie **Benutzer** aus.
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Wählen Sie, welche Benutzer Sie bearbeiten möchten.
    
5. Wählen Sie im rechten Bereich **Bearbeiten** aus.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Klicken Sie auf der Seite **Allgemeine** Optionen aktivieren Sie oder deaktivieren Sie das Kontrollkästchen neben den Features, den, die Sie ändern möchten, und wählen Sie dann auf **Speichern**.
    
|**Option**|**Beschreibung**|
|:-----|:-----|
|Audio und HD-Video  <br/> |Diese Person audio Besprechungen aufzuzeichnen, Audio- und Videodaten Besprechungen zulassen oder nicht ermöglicht es ihnen, Planen Sie eine beliebige Meeetings (kein Rahmen).  <br/> |
|Aufzeichnen von Unterhaltungen und Besprechungen  <br/> |Wählen Sie diese Person zulässigen Werte zum Aufzeichnen.  <br/> Diese Option ist nicht mit Skype für Business Basic verfügbar.  <br/> |
|Deaktivieren Sie für die Kompatibilität Features nicht archiviert  <br/> | Wählen Sie diese Option, wenn Sie gesetzlich vorgeschrieben auf elektronischem Wege gespeicherten Informationen zu erhalten. <br/>  Durch Auswählen dieser Option wird deaktiviert Features, die erfasst werden nicht, wenn Sie eine [Compliance-Archiv](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) im Exchange Administrationscenter in eingerichtet haben. Die folgenden Features deaktiviert: <br/>  Dateiübertragung mittels Chat <br/>  Freigegebene OneNote-Seiten <br/>  PowerPoint-Anmerkungen <br/> |
   
Verwenden Sie zum Konfigurieren dieser Einstellungen in einer Sammeloperation PowerShell. Finden Sie unter [Verwalten von Richtlinien in Skype für Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).
  
## <a name="block-external-communications"></a>Externe Kommunikation blockieren
<a name="__toc325019206"> </a>

Nachdem Sie für alle Benutzer in Ihrem Unternehmen [können Skype für Unternehmensbenutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md) können Sie die externe Kommunikation für bestimmte Personen mit den folgenden Schritten selektiv blockieren.
  
1. Wählen Sie **Benutzer**, wählen Sie die Benutzer, dessen Einstellungen Sie deaktivieren möchten, und wählen Sie dann auf **Bearbeiten** ![bearbeiten](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Wählen Sie die **externe Kommunikation**, und deaktivieren Sie die Optionen nach Bedarf:
    
  - **Externe Skype für Unternehmensbenutzer**: Deaktivieren Sie dieses Kontrollkästchen, wenn Sie nicht, dass den Benutzer mit Skype für Unternehmensbenutzer in verbunddomänen kommunizieren können möchten.
    
  - **Externe Skype-Benutzer**: Deaktivieren Sie dieses Kontrollkästchen, wenn Sie nicht möchten, dass den Benutzer mit Personen kommunizieren, die die app FreeSkype verwenden können.
    
3. Klicken Sie auf **Speichern**.
    
Verwenden Sie zum Konfigurieren dieser Einstellungen in einer Sammeloperation PowerShell. Finden Sie unter [Verwalten der Kommunikation in Skype für Business Online mit externen Benutzern und Organisationen](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Bearbeiten von Audiokonferenzen-Einstellungen für einen Benutzer
<a name="__toc314837483"> </a>

1. Wählen Sie **Benutzer**aus, wählen Sie den Benutzer, dessen Sie um zu bearbeiten, WAN-Audiokonferenzen Einstellungen, und wählen Sie dann auf **Bearbeiten** ![bearbeiten](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Wählen Sie **Audiokonferenzen**, wählen Sie Ihren Audiokonferenz-Anbieter, geben Sie oder ändern Sie die angeforderte Informationen, und klicken Sie dann auf **Speichern**.
    
|**Audiokonferenzeinstellung**|**Beschreibung**|
|:-----|:-----|
|**Name des Anbieters** <br/> |Wählen Sie aus der Liste der Anbieter.  <br/> |
|**Gebührenpflichtige Nummer** (erforderlich) <br/> |Für ein Drittanbieter-ACP sind diese Rufnummern diejenigen aus, die Sie vom Anbieter von Audiokonferenzen erhalten haben. Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet wird, werden diese Zahlen, die für die audiokonferenzbrücke festgelegt werden. Formatieren Sie die Zahlen in Skype für Geschäfts- und Microsoft-Teams, Besprechungsanfragen angezeigt werden soll.  <br/> |
|**Gebührenfreien Nummer** <br/> |Für ein Drittanbieter-ACP sind diese Rufnummern diejenigen aus, die Sie vom Anbieter von Audiokonferenzen erhalten haben. Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet wird, werden diese Zahlen, die für die audiokonferenzbrücke festgelegt werden. Formatieren Sie die Zahlen in Skype für Geschäfts- und Microsoft-Teams, Besprechungsanfragen angezeigt werden soll.  <br/> |
|**Konferenz-ID und PIN-Nummer** (erforderlich) <br/> |Die Teilnehmer PIN oder Konferenz Code verwendet, um an Besprechungen teilnehmen, die von diesem Benutzer geplant werden und werden von einem Drittanbieter-Audiokonferenz-Anbieter bereitgestellt. Wenn der Benutzer Microsoft als Audiokonferenz-Anbieter verwendet, wird nicht erforderlich sein.  <br/> |
   
Verwenden Sie zum Konfigurieren dieser Einstellungen in einer Sammeloperation PowerShell. Finden Sie unter [Einrichten des Telefons, Zahlen auf enthalten lädt](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).


[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Verwandte Themen 

[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
