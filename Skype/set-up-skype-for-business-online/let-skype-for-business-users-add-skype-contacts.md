---
title: "Können Sie Skype für Unternehmensbenutzer Skype-Kontakte hinzufügen"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: "Finden Sie unter Besucher, Skype für Business Contact Skype für Unternehmensbenutzer von außerhalb Ihrer Organisation verwenden, und fügen sie Sie ihrer Liste Kontakte hinzu. "
ms.openlocfilehash: 1add1f6e907613d1ac536c92b57cfce7f3cdaf66
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>Können Sie Skype für Unternehmensbenutzer Skype-Kontakte hinzufügen

Mit Skype für Unternehmen, Ihre Benutzer können nach suchen und Sofortnachrichten mit jeder, der Skype, kostenlose app verwendet! In diesem Artikel wird erläutert, was Sie benötigen hierzu Skype-Kontakte hinzugefügt werden können. 
  
Sie benötigen [Administratorberechtigungen](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 dazu.
  
1. Melden Sie sich mit Ihrem Office 365 Admin-Konto im [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).
    
2. Wechseln Sie in das Office 365 Administrationscenter zu **Admin Center** > **Skype für Unternehmen**. 
    
    ![Wählen Sie die Skype für Business Administrationscenter.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. Wählen Sie in der **Skype für Business Administrationscenter**, **Organisation** > **externe Kommunikation**. 
    
4. Standardmäßig können die Benutzer mit allen anderen Personen in der ganzen Welt kommunizieren, die Skype für Unternehmen (vorausgesetzt, dass die Firewall dafür konfiguriert wurde) verwenden. 
    
    ![Wählen Sie Let Personen Skype für Unternehmen zur Kommunikation mit Skype verwenden.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    Wenn die Benutzer sollen chatten mit Skype-Benutzern, aber nicht sollen chatten mit anderen Skype für Unternehmen verwenden, wählen Sie **auf nur für zulässige Domänen**. Wenn Sie Kontakt mit Skype-Benutzern aktivieren, wird automatisch skype.com als zulässige Domäne im Hintergrund hinzugefügt. 
    
    Wenn Sie den Kontakt aus allen anderen Unternehmen in der ganzen Welt Verwendung Skype für Unternehmen, mit Ausnahme von bestimmten Netzwerken zulassen, und wählen Sie möchten **auf mit Ausnahme der blockierten Domänen**, und wählen Sie **+** diese Domänen hinzufügen. Jeder werden Kontakt zu Ihnen aufnehmen, mit Ausnahme von Personen in diesen bestimmten Domänen können. (Möglicherweise einige Unternehmen diese Option wählen, beispielsweise, wenn sie in der Aufbewahrung für eventuelle sind und, um sicherzustellen, dass müssen es besteht keine Verbindung mit den anderen Business).
    
5. Wählen Sie auf **Benutzer dürfen Skype für die geschäftliche Kommunikation mit Skype-Benutzern außerhalb Ihrer Organisation zu verwenden**. 
    
6.  Wenn Sie Windows-Firewall verwenden, werden die erforderlichen Ports in Skype für Unternehmen automatisch geöffnet.
    
    Wenn Ihre Organisation eine andere Lösung verwendet, um zu verhindern, dass die Computer in Ihrem Netzwerk verbinden mit dem Internet, stellen Sie sicher, dass Clientcomputer alle die [IP-Adressen und URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) für Skype-Konnektivität und Skype-Verzeichnissuche zugreifen zu können. Dies erfordert möglicherweise hinzufügen und Sie auf die ausgehenden Zulassungsliste in Ihrer Firewall oder der Proxyserver Infrastruktur-Konfiguration.
    
7. **So testen Sie bis zu 24 Stunden zu warten**. Jeder Änderung von den Einstellungen für externe Kommunikation dauert es bis zu 24 Stunden, damit die Änderungen in den Rechenzentren aufgefüllt.
    
8. Zeigen Sie Ihren Benutzern wie Suchen und Hinzufügen von Skype-Kontakte in ihrer Liste Skype für Geschäftskontakten. Zeigen sie für die [Suche nach Personen in Skype für Unternehmen](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).
    
## <a name="test-and-troubleshoot"></a>Tests und Problembehandlung

Um die Installation zu testen, benötigen Sie einen Kontakt auf Skype, die nicht hinter der Firewall Ihres Unternehmens ist. Sie können bei Skype von Google Mail-Konto: Outlook.com-Konto oder andere Art von e-Mail-Konto angemeldet sein.
  
1. Nachdem ändern Sie die Einstellungen für externe Kommunikation, **Warten Sie, bis zu 24 Stunden zu testen**.
    
2. Abmelden bei Skype für Unternehmen und dann wieder anmelden, damit Sie die Option zum Durchsuchen des Verzeichnisses Skype angezeigt. 
    
    ![Wenn Skype Directory hervorgehoben ist, können Sie nach Personen suchen, die über Skype-Konten verfügen.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. In Skype für Unternehmen die für Ihre Kontakte Skype suchen Sie aus, und senden Sie eine Anforderung zum chat. 
    
    Wenn Sie die Nachricht, die aufgrund der Unternehmensrichtlinie gesendet werden konnte erhalten, müssen Sie die [Firewalleinstellungen](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)überprüfen. 
    
4. Wenden Sie eine andere Möglichkeit zu prüfen, ob das Problem besteht, dass Ihre Firewall aktiviert ist darin, gehen Sie an einem Speicherort Wifi nicht hinter der Firewall wie einem Café und Skype für Unternehmen zum Senden einer Anforderung an die Skype verwenden Chat. 
    
  - **Wenn Sie Ihren Skype Kontakt eine Anforderung gesendet und sie nie empfangen**, bitten Sie eine Anforderung zum chat senden. Wenn das Problem Herstellen einer Verbindung zwischen Skype und Skype für Unternehmen wurde, löst, die häufig es.
    
  - Wenn die Nachricht im Café durchläuft, aber nicht, wenn Sie im Büro sind, klicken Sie dann Sie, das Problem wissen ist jetzt Ihrer Firewall. 
    
## <a name="what-you-can-and-cant-do"></a>Was Sie tun können und ist nicht möglich

- **Skype für Unternehmen auf Mac** haben nicht die Möglichkeit zum Suchen nach und kommunizieren mit Skype-Kontakte.
    
- Während Sie suchen nach und Skype-Benutzer gefunden werden können, keine, suchen und Skype für Unternehmensbenutzer suchen. Sie müssen dies eine Kontaktanfrage veranlassen und melden Sie sich bei Skype und akzeptieren, bevor Sie Sofortnachrichten mit ihnen können lassen. 
    
- Es ist nicht möglich, Instant Messaging-Diensten mit anderen Sofortnachrichten-Dienstanbietern wie Google oder Facebook zulassen. Skype für Unternehmen können Textnachrichten Mobiltelefon senden.
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>Welche Funktionen sind verfügbar, wenn Sie Skype-Kontakte hinzufügen?

Skype-Kontakte, die mit ihren Microsoft-Konto (früher Windows Live ID) signiert finde einige, jedoch nicht alle Features, wenn sie mit Ihrer Skype für Unternehmensbenutzer kommunizieren.
  
|**Verfügbar mit Skype-Kontakte**|**Mit Skype-Kontakte nicht verfügbar.**|
|:-----|:-----|
| Video-Unterhaltungen <br/>  Person-Sofortnachrichten <br/>  Anwesenheit <br/> | Sofortnachrichtenunterhaltungen mit mehreren Teilnehmern <br/>  Audio und video Unterhaltungen mit mindestens drei Personen <br/>  Desktop- und Programmfreigabe verwenden <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Verwandte Themen

[Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren](allow-users-to-contact-external-skype-for-business-users.md)
  
[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)
