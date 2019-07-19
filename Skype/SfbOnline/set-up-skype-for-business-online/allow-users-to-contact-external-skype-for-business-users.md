---
title: Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
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
ms.openlocfilehash: 570861f532371dc8eca253956ffdd200e60f5990
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792684"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren

> [!NOTE]
> Die Skype for Business-Föderation steht nicht für Office 365 zur Verfügung, das von 21Vianet und Office 365 Germany-Organisationen betrieben wird. 
  
Führen Sie die Schritte in diesem Artikel in folgenden Fällen aus:
  
- In Ihrem Unternehmen befinden sich Benutzer in verschiedenen Domänen. Beispiel: Rob@ContosoEast.com und Ann@ContosoWest.com.
    
- Sie möchten den Personen in Ihrer Organisation die Möglichkeit geben, Skype for Business zu verwenden, um Personen in bestimmten Unternehmen außerhalb Ihrer Organisation zu kontaktieren.
    
- Sie möchten, dass andere Personen in der Welt, die Skype for Business nutzen, Sie mit Ihrer e-Mail-Adresse finden und mit Ihnen Kontakt aufnehmen können. Wenn Sie und die anderen Benutzer die Standardeinstellungen für Skype for Business verwenden, funktioniert dies automatisch. Anderenfalls müssen sie sicherstellen, dass Ihre Domäne nicht durch ihre Konfiguration blockiert wird.
    
## <a name="enable-business-to-business-communications-for-your-users"></a>Aktivieren der Business-to-Business-Kommunikation für die Benutzer
<a name="bk_preview"> </a>

Sie benötigen [Administratorberechtigungen](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in beiden Organisationen, um dies zu tun.

![Ein Symbol, das das Microsoft Teams](../images/teams-logo-30x30.png) -Logo **mit dem Team Admin Center** zeigt
  
1. Registrieren Sie sich mit Ihrem Office 365-Administratorkonto. 
    
2. Wechseln Sie im Admin Center zu **Admin Center** > **Teams**.
    
    ![Wählen Sie den Team-Administrator aus.](../images/MS-Teams-Admin.png)
  
3. Wählen Sie im **Teamcenter** **Skype** > **Legacy Portal** 
 ![aus, und wählen Sie das SFB Legacy-Portal aus.](../images/SFBlegacy-size65.png)
 
4. Wählen Sie im **Skype for Business Admin Center** die Option **Organisation** > **External Communications**aus.
5. Um die Kommunikation mit einem bestimmten Unternehmen oder mit Benutzern in einer anderen Domäne einzurichten, wählen Sie im Dropdownfeld **nur für zulässige Domänen**aktivieren aus.
    
    ODER wählen Sie, wenn Sie die Kommunikation mit allen anderen Unternehmen aktivieren möchten, die über offene Skype for Business-Richtlinien verfügen, die Option **Aktivieren mit Ausnahme der blockierten Domänen** aus. Dies ist die Standardeinstellung.
    
6. Wählen **+** Sie unter **blockierte oder zulässige Domänen**den Namen der Domäne aus, die Sie zulassen möchten, und fügen Sie ihn hinzu.
    
7. Stellen Sie sicher, dass der Administrator in der anderen Organisation die gleichen Schritte in Ihrem **Skype for Business Admin Center**durchführt. Beispiel: In der Liste der **zugelassenen Domänen** muss der Administrator der anderen Organisation die Domäne für Ihr Unternehmen eingeben.
    
8. Wenn Sie die Windows-Firewall verwenden, öffnet Skype for Business die erforderlichen Ports automatisch.
    
    Wenn Ihre Organisation die Internetverbindung von Computern in Ihrem Netzwerk mit einer anderen Firewall-Lösung einschränkt, vergewissern Sie sich, dass Ihre Clientcomputer auf die folgenden [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) zugreifen können. Dies erfordert möglicherweise das Hinzufügen der FQDNs zur ausgehenden Zulassungsliste in Ihrer Firewall-oder Proxy Infrastruktur \*Konfiguration: ** \*API.Skype.com**, **users.Storage.Live.com**und **Graph.Skype.com**. Anweisungen zum Öffnen dieser Ports in Ihrer Firewall finden Sie in der Begleitdokumentation.
    
    Eine Liste aller Ports, die Sie öffnen müssen, finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).

9. Stellen Sie sicher, dass der Administrator in der Organisation auch die folgenden Schritte ausgeführt hat.
    
10. **WARTEN SIE MIT DEM TEST BIS ZU 24 STUNDEN**. Bei jeder Änderung der Einstellungen für externe Kommunikation kann es bis zu 24 Stunden dauern, bis die Änderungen in allen Rechenzentren übernommen wurden.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Sie können Ihren Benutzern jetzt die Möglichkeit geben, nach beliebigen Benutzern von Skype, der kostenlosen Heimanwender-App, zu suchen und Chatnachrichten mit ihnen auszutauschen! Weitere Informationen finden Sie unter [zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md).
  
## <a name="test-and-troubleshoot"></a>Tests und Problembehandlung
<a name="bk_preview"> </a>

 **Am häufigsten haben Benutzer beim Einrichten der Kommunikation zwischen Unternehmen Probleme damit, die [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) richtig festzulegen.**
  
Um Ihr Setup zu testen, benötigen Sie einen Kontakt in Skype for Business, der sich nicht hinter der Firewall Ihrer Firma befindet.
  
1. Warten Sie nach einer Änderung der Einstellungen für externe Kommunikation **BIS ZU 24 STUNDEN, BEVOR SIE TESTS DURCHFÜHREN**.
    
2. Suchen Sie in Skype for Business nach Ihrem Kontakt in Skype for Business, und senden Sie eine Chatanfrage.
    
    Wenn Sie eine Meldung erhalten, dass Sie aufgrund einer Unternehmensrichtlinie nicht gesendet werden konnte, müssen Sie Ihre [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)doppelt überprüfen.
    
3. Bitten Sie Ihren Skype for Business-Kontakt, Ihnen eine Chatanfrage zu senden. Wenn Sie die Anfrage nicht erhalten, stellen die Firewalleinstellungen das Problem dar (dabei wird angenommen, dass der Kontakt bereits die Richtigkeit seiner Firewalleinstellungen überprüft hat).
    
4. Eine weitere Möglichkeit, zu testen, ob die Firewall das Problem darstellt: Gehen Sie zu einem Ort mit WLAN, der sich nicht hinter Ihrer Firewall befindet (zum Beispiel in ein Café), und senden Sie mit Skype for Business eine Chatanfrage an Ihren Kontakt. Wenn die Nachricht dort gesendet wird, an Ihrem Arbeitsplatz aber nicht, wissen Sie, dass die Firewall das Problem darstellt.
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Beim Herstellen einer Verbindung mit einem anderen Unternehmen andere Personen finden und selbst gefunden werden
<a name="bk_preview"> </a>

Nachdem Sie die externe Kommunikation mit anderen Skype for Business-Benutzern aktiviert haben, können Ihre Benutzer Partner von Skype for Business-Benutzern finden, indem Sie nach Ihrem Anmeldenamen suchen, beispielsweise Rob@contoso.com. Anschließend müssen sie die Person zu ihrer Kontaktliste hinzufügen.
  
![Wenn Sie einen Benutzer in einem Verbundunternehmen suchen möchten, müssen Sie nach seiner e-Mail-Adresse suchen (Dies ist in der Regel auch der Name der Anmeldung).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Tipps zum Einrichten der Kommunikation mit Partnerunternehmen
<a name="bk_preview"> </a>

- Informationen zum Konfigurieren des Verbunds zwischen Skype for Business 2015 und Skype for Business Online finden Sie in diesem Artikel: [Konfigurieren des Föderations Kontakts mit Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Informationen zum Konfigurieren des Verbunds zwischen lync und Skype for Business Online finden Sie in diesem Artikel: [Konfigurieren der Föderations Unterstützung für einen lync Online-Kunden](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Wenn zwei Skype for Business-Benutzer in Office 365 auf verschiedenen Domänen miteinander kommunizieren, können sie nur Skype for Business-Funktionen nutzen, die in beiden Organisationen aktiviert wurden (zum Beispiel Videounterhaltung oder Desktopfreigabe).
    
- Wenn ein Skype for Business-Benutzer in Ihrer Organisation an einem in-situ-oder Litigation-Speicher platziert wird, werden alle Chat Unterhaltungen zwischen diesem Nutzer und anderen Skype for Business-oder Skype-Benutzern in **wiederherstellbaren Elementen** in Ihrem Postfach gespeichert. Diese Unterhaltungen werden nicht im Ordner **Aufgezeichnete Unterhaltungen** in ihrem Postfach gespeichert.
    
## <a name="turn-off-external-communication-for-specific-individuals"></a>Externe Kommunikation für bestimmte Personen deaktivieren
<a name="bk_preview"> </a>

Nachdem Sie die externe Kommunikation für Ihr gesamtes Unternehmen aktiviert haben, können Sie sie für bestimmte Personen deaktivieren.
  
1. Registrieren Sie sich mit Ihrem Office 365-Administratorkonto.
    
2. Wechseln Sie im Admin Center zu **Benutzer** > **aktive**Benutzer.
    
3. Klicken Sie in der Liste der Benutzer auf den Benutzer und dann unter **Weitere Einstellungen** auf **Skype for Business-Eigenschaften bearbeiten**.
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. Wählen Sie im **Skype for Business Admin Center**die Option **externe Kommunikation**aus.
    
    Auf der Seite " **Optionen** " werden alle Auswahlmöglichkeiten ausgewählt. Deaktivieren Sie die Kommunikation, die Sie deaktivieren möchten. Die folgende Abbildung zeigt, dass Jakob mit Personen in anderen vertrauenswürdigen Unternehmen kommunizieren kann, darüber hinaus jedoch nicht mit anderen Skype-Nutzern.
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Klicken Sie auf **Speichern**.
    
> [!NOTE]
> Sie müssen ggf. bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden. 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a>Verwandte Themen
<a name="bk_preview"> </a>

[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)
  
[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
