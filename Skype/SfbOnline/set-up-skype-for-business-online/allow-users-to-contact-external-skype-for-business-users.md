---
title: Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
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
description: 'See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. '
ms.openlocfilehash: b7700eeaf9a2fdd39d9a25fce93cfd17f42d4b8e
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren

> [!NOTE]
> Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations. 
  
Führen Sie die Schritte in diesem Artikel in folgenden Fällen aus:
  
- In Ihrem Unternehmen befinden sich Benutzer in verschiedenen Domänen. Beispiel: Rob@ContosoEast.com und Ann@ContosoWest.com.
    
- Sie möchten den Personen in Ihrer Organisation die Möglichkeit geben, Skype for Business zu verwenden, um Personen in bestimmten Unternehmen außerhalb Ihrer Organisation zu kontaktieren.
    
-You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address. Wenn Sie und die anderen Benutzer die Standardeinstellungen für Skype for Business verwenden, funktioniert dies automatisch. Anderenfalls müssen sie sicherstellen, dass Ihre Domäne nicht durch ihre Konfiguration blockiert wird.
    
## <a name="enable-business-to-business-communications-for-your-users"></a>Aktivieren der Business-to-Business-Kommunikation für die Benutzer
<a name="bk_preview"> </a>

To see how this works, watch this video:
***
> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=492278f0-6912-47ba-a1d1-00040061cf44&AutoPlayVideo=false]
***

You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.
  
1. Sign in with your Office 365 admin account. 
    
2. Gehen Sie in Office 365 Admin Center zu **Admin Center** > **Skype for Business**.
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. Wählen Sie unter **Skype for Business Admin Center**die Option **Organisation** > **Externe Kommunikation**.
    
4. To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.
    
    ODER wählen Sie, wenn Sie die Kommunikation mit allen anderen Unternehmen aktivieren möchten, die über offene Skype for Business-Richtlinien verfügen, die Option **Aktivieren mit Ausnahme der blockierten Domänen** aus. Dies ist die Standardeinstellung.
    
5. Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.
    
6. Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**. Beispiel: In der Liste der **zugelassenen Domänen** muss der Administrator der anderen Organisation die Domäne für Ihr Unternehmen eingeben.
    
7. Wenn Sie die Windows-Firewall verwenden, öffnet Skype for Business die erforderlichen Ports automatisch.
    
    Wenn Ihre Organisation die Internetverbindung von Computern in Ihrem Netzwerk mit einer anderen Firewall-Lösung einschränkt, vergewissern Sie sich, dass Ihre Clientcomputer auf die folgenden [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) zugreifen können. This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**. For instructions on how to open these ports in your firewall, check the documentation that came with it.
    
    For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).

8. Make sure that the administrator in the organization has also followed these steps.
    
9. **WARTEN SIE MIT DEM TEST BIS ZU 24 STUNDEN**. Bei jeder Änderung der Einstellungen für externe Kommunikation kann es bis zu 24 Stunden dauern, bis die Änderungen in allen Rechenzentren übernommen wurden.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Sie können Ihren Benutzern jetzt die Möglichkeit geben, nach beliebigen Benutzern von Skype, der kostenlosen Heimanwender-App, zu suchen und Chatnachrichten mit ihnen auszutauschen! To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).
  
## <a name="test-and-troubleshoot"></a>Tests und Problembehandlung
<a name="bk_preview"> </a>

 **Am häufigsten haben Benutzer beim Einrichten der Kommunikation zwischen Unternehmen Probleme damit, die [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) richtig festzulegen.**
  
Um Ihr Setup zu testen, benötigen Sie einen Kontakt in Skype for Business, der sich nicht hinter der Firewall Ihrer Firma befindet.
  
1. Warten Sie nach einer Änderung der Einstellungen für externe Kommunikation **BIS ZU 24 STUNDEN, BEVOR SIE TESTS DURCHFÜHREN**.
    
2. Suchen Sie in Skype for Business nach Ihrem Kontakt in Skype for Business, und senden Sie eine Chatanfrage.
    
    If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).
    
3. Bitten Sie Ihren Skype for Business-Kontakt, Ihnen eine Chatanfrage zu senden. Wenn Sie die Anfrage nicht erhalten, stellen die Firewalleinstellungen das Problem dar (dabei wird angenommen, dass der Kontakt bereits die Richtigkeit seiner Firewalleinstellungen überprüft hat).
    
4. Eine weitere Möglichkeit, zu testen, ob die Firewall das Problem darstellt: Gehen Sie zu einem Ort mit WLAN, der sich nicht hinter Ihrer Firewall befindet (zum Beispiel in ein Café), und senden Sie mit Skype for Business eine Chatanfrage an Ihren Kontakt. Wenn die Nachricht dort gesendet wird, an Ihrem Arbeitsplatz aber nicht, wissen Sie, dass die Firewall das Problem darstellt.
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Beim Herstellen einer Verbindung mit einem anderen Unternehmen andere Personen finden und selbst gefunden werden
<a name="bk_preview"> </a>

After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com. Then they will need to add the person to their list of contacts.
  
![To find a user in a federated business, you must search for their email address (this is usually also their sign in name).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Tipps zum Einrichten der Kommunikation mit Partnerunternehmen
<a name="bk_preview"> </a>

- Informationen zum Konfigurieren des Verbunds zwischen Skype for Business 2015 und Skype for Business Online finden Sie in folgendem TechNet-Artikel: [Konfigurieren eines Partnerverbunds in Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Informationen zum Konfigurieren des Verbunds zwischen Lync und Skype for Business Online finden Sie in folgendem TechNet-Artikel: [Konfigurieren der Unterstützung für einen Partnerverbund mit einem Lync Online-Kunden](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Wenn zwei Skype for Business-Benutzer in Office 365 auf verschiedenen Domänen miteinander kommunizieren, können sie nur Skype for Business-Funktionen nutzen, die in beiden Organisationen aktiviert wurden (zum Beispiel Videounterhaltung oder Desktopfreigabe).
    
- If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox. Diese Unterhaltungen werden nicht im Ordner **Aufgezeichnete Unterhaltungen** in ihrem Postfach gespeichert.
    
## <a name="turn-off-external-communication-for-specific-individuals"></a>Externe Kommunikation für bestimmte Personen deaktivieren
<a name="bk_preview"> </a>

Nachdem Sie die externe Kommunikation für Ihr gesamtes Unternehmen aktiviert haben, können Sie sie für bestimmte Personen deaktivieren.
  
1. Sign in with your Office 365 admin account.
    
2. In the Office 365 admin center, go to **Users** > **Active users**.
    
3. Klicken Sie in der Liste der Benutzer auf den Benutzer und dann unter **Weitere Einstellungen** auf **Skype for Business-Eigenschaften bearbeiten**.
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. In the **Skype for Business admin center**, choose **External communications**.
    
    On the **Options** page, all of the choices will be selected. Clear the communications you want to disable. Die folgende Abbildung zeigt, dass Jakob mit Personen in anderen vertrauenswürdigen Unternehmen kommunizieren kann, darüber hinaus jedoch nicht mit anderen Skype-Nutzern.
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Klicken Sie auf **Speichern**.
    
> [!NOTE]
> Sie müssen ggf. bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden. 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a>Verwandte Themen
<a name="bk_preview"> </a>

[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)
  
[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
