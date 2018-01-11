---
title: "Zulassen, dass Benutzer wenden Sie sich an externe Skype für Unternehmensbenutzer"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: "Finden Sie unter Konfigurieren von Skype für Unternehmen, damit Benutzer mit Benutzern in anderen Organisationen kommunizieren oder außerhalb der für diese Kontakte können. "
ms.openlocfilehash: e21b89c24618d2296dc44766b8d6ddbd3d527ef7
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Zulassen, dass Benutzer wenden Sie sich an externe Skype für Unternehmensbenutzer

> [!NOTE]
> Skype für den Verbund Business nicht zu Office 365 handelt, das von 21Vianet und Office 365 Deutschland Organisationen zur Verfügung. 
  
Verwenden Sie die Schritte in diesem, wenn Artikel:
  
- Sie müssen die Benutzer in verschiedenen Domänen in Ihrem Unternehmen. Rob@ContosoEast.com und Ann@ContosoWest.com.
    
- Sie möchten die Personen in Ihrer Organisation mit Skype für Unternehmen wenden Sie sich an Personen in bestimmten Unternehmen außerhalb Ihrer Organisation.
    
-Sie möchten andere Person in der ganzen Welt, die Skype für Unternehmen verwendet, in der Lage, zu finden, und wenden Sie sich mithilfe Ihrer e-Mail-Adresse sein. Wenn Sie und sie die Standardeinstellung Skype für Business Einstellungen verwenden, funktioniert dies automatisch. Wenn dies nicht der Fall, müssen sie sicherstellen, dass die Konfiguration Ihrer Domäne blockieren nicht zur Verfügung.
    
## <a name="enable-business-to-business-communications-for-your-users"></a>Aktivieren Sie Business-Geschäftskommunikation für Ihre Benutzer
<a name="bk_preview"> </a>

Sie benötigen [Administratorberechtigungen](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 dazu.
  
1. Melden Sie sich mit Ihrem Office 365-Admin-Konto. 
    
2. Wechseln Sie in das Office 365 Administrationscenter zu **Admin Center** > **Skype für Unternehmen**.
    
    ![Wählen Sie die Skype für Business Administrationscenter.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. Wählen Sie in der **Skype für Business Administrationscenter**, **Organisation** > **externe Kommunikation**.
    
4. Zum Einrichten der Kommunikation mit einem bestimmten Unternehmen oder mit Benutzern in einer anderen Domäne, in der Dropdown-Feld auswählen **auf nur für zulässige Domänen**.
    
    ODER, um die Kommunikation mit allen anderen in der ganzen Welt ermöglichen, die geöffnet ist Skype für Geschäftsrichtlinien, wählen Sie **auf mit Ausnahme der blockierten Domänen**. Dies ist die Standardeinstellung.
    
5. Wählen Sie unter **blockiert oder zugelassenen Domänen**, **+** , und fügen Sie den Namen der Domäne, die Sie zulassen möchten.
    
6. Stellen Sie sicher, dass der Administrator in der anderen Organisation dieselben Schritte in ihrer **Skype für Business Administrationscenter**ist. Beispielsweise muss in ihrer Liste der **zulässigen Domänen** ihre Admin die Domäne für Ihr Unternehmen eingeben.
    
7. Wenn Sie Windows-Firewall verwenden, werden die erforderlichen Ports in Skype für Unternehmen automatisch geöffnet.
    
    Wenn Ihre Organisation eine andere Firewall-Lösung um zu verhindern, dass die Computer in Ihrem Netzwerk verbinden mit dem Internet verwendet wird, stellen Sie sicher, dass die Client-Computer die folgenden [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)zugreifen können. Es kann erforderlich sein, die FQDNs, die ausgehende Zulassungsliste in die Firewall oder der Proxy Infrastruktur-Konfiguration hinzufügen: ** \*. api.skype.com**, \* **. users.storage.live.com**, und **graph.skype.com**. Überprüfen Sie für Informationen dazu, wie Sie diese Ports in der Firewall zu öffnen die Begleitdokumentation es.
    
    Eine Liste aller Ports, die Sie öffnen möchten, finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).
    
8. **So testen Sie bis zu 24 Stunden zu warten**. Jeder Änderung von den Einstellungen für externe Kommunikation dauert es bis zu 24 Stunden, damit die Änderungen in den Rechenzentren aufgefüllt.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Sie können die Benutzer zum Suchen und Instant Messaging mit jeder, der Skype, die kostenlose Consumer-app verwendet! Finden Sie weitere Informationen finden Sie unter [Let Skype für Unternehmensbenutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md).
  
## <a name="test-and-troubleshoot"></a>Tests und Problembehandlung
<a name="bk_preview"> </a>

 **Das am häufigsten verwendete Problem, Personen, beim Einrichten von Business Geschäftskommunikation auftreten, ist ihre [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) rechten abrufen.**
  
Um die Installation zu testen, benötigen Sie einen Kontakt auf Skype für Unternehmen, die nicht hinter der Firewall Ihres Unternehmens ist.
  
1. Nachdem ändern Sie die Einstellungen für externe Kommunikation, **Warten Sie, bis zu 24 Stunden zu testen**.
    
2. Suchen Sie in Skype für Unternehmen nach dem Kontakt in Skype für Unternehmen, und senden Sie eine Anforderung zum chat.
    
    Wenn Sie eine Meldung, die aufgrund der Unternehmensrichtlinie gesendet werden konnte erhalten, müssen Sie Ihre [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)überprüfen.
    
3. Bitten Sie Ihre Skype für Business Contact senden eine Anforderung an chat. Wenn Sie ihre Anforderung erhalten, wird das Problem Einstelllungen Firewall (vorausgesetzt, sie haben bereits bestätigt, dass ihre Firewalleinstellungen korrekt sind).
    
4. Eine andere Möglichkeit zu prüfen, ob das Problem der Firewall ist ist, gehen Sie an einem Speicherort Wifi nicht hinter der Firewall wie einem Café und Skype für Unternehmen das Senden einer Anforderung an den Kontakt zu chat verwenden. Wenn die Meldung Es durchläuft, aber nicht, wenn Sie im Büro sind, klicken Sie dann Sie, das Problem wissen ist die Firewall.
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Wie andere Personen finden und gefunden werden, beim Herstellen einer Verbindung mit einem anderen Unternehmen
<a name="bk_preview"> </a>

Nachdem Sie die externe Kommunikation mit anderen Skype für Unternehmensbenutzer aktivieren, Ihre Benutzer können Verbund Skype für Unternehmensbenutzer anhand suchen für ihren Anmeldenamen ein: beispielsweise Rob@contoso.com. Klicken Sie dann müssen sie die Person zu ihrer Liste Kontakte hinzuzufügen.
  
![Wenn einen Benutzer in einer verbundgeschäftspartner suchen möchten, müssen Sie ihre e-Mail-Adresse suchen (Dies ist in der Regel auch ihre-Anmeldename).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Tipps zur Einrichtung der Kommunikation mit federated Unternehmen
<a name="bk_preview"> </a>

- Konfigurieren von Verbund zwischen Skype für Business 2015 und Skype für Business Online finden Sie in dieser TechNet-Artikel: [Configure Verbund mit Skype für Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Um zwischen Lync und Skype-Verbund für Business Online zu konfigurieren, finden Sie unter TechNet-Artikel: [Configuring Federation Support für Lync Online-Kunden](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Wenn zwei Skype für Unternehmensbenutzer in Office 365 sind in unterschiedlichen Domänen miteinander kommunizieren, können sie nur Skype für Business-Features (beispielsweise videounterhaltungen oder Desktopfreigabe) verwenden, die in beiden Organisationen aktiviert sind.
    
- Wenn eine Skype für Business-Benutzer in Ihrer Organisation für eine In-Place oder Aufbewahrung für eventuelle Rechtsstreitigkeiten festgelegt wird, werden alle Sofortnachrichtenunterhaltungen zwischen diesem Benutzer und andere Skype für Business oder Skype-Benutzer in **Wiederherstellbare Elemente** in ihrem Postfach gespeichert. Diese Gespräche werden nicht im Verlaufsordner **Unterhaltungen** in ihrem Postfach gespeichert.
    
## <a name="turn-off-external-communication-for-specific-individuals"></a>Deaktivieren der externen Kommunikation für den bestimmten Einzelpersonen
<a name="bk_preview"> </a>

Nachdem Sie die externe Kommunikation für das gesamte Unternehmen aktivieren, können Sie sie nur bestimmten Personen deaktivieren.
  
1. Melden Sie sich mit Ihrem Office 365-Admin-Konto.
    
2. Wechseln Sie in das Office 365 Administrationscenter zu **Benutzern** > **aktive Benutzer**.
    
3. Klicken Sie in der Liste der Benutzer wählen Sie den Benutzer, und klicken Sie unter **Weitere Einstellungen** **Skype für Business Eigenschaften bearbeiten**.
    
    ![Wählen Sie Skype für Unternehmen](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. Wählen Sie in der **Skype für Business Administrationscenter** **externe Kommunikation**.
    
    Auf der Seite **Optionen** werden alle Optionen ausgewählt werden. Deaktivieren Sie die Kommunikation, die Sie deaktivieren möchten. Die folgende Abbildung zeigt, dass Jakob mit Personen in anderen vertrauenswürdigen Unternehmen, aber nicht mit anderen Skype-Benutzern kommunizieren kann.
    
    ![Wählen Sie externe Kontakte](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Klicken Sie auf **Speichern**.
    
> [!NOTE]
> Möglicherweise müssen Sie warten, bis zu 24 Stunden, damit die Änderungen wirksam werden. 
  


[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a>Verwandte Themen
<a name="bk_preview"> </a>

[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)
  
[Können Sie Skype für Unternehmensbenutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)
  

