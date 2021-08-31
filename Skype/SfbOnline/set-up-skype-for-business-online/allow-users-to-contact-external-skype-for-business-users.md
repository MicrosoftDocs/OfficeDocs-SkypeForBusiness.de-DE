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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: 'Erfahren Sie, wie sie Skype for Business, damit Benutzer mit Benutzern in einer anderen Organisation sprechen oder externe Kontakte mit ihnen sprechen können. '
ms.openlocfilehash: e98f30718bb44a3ca2e5f48560d7f38552a2ef49
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731114"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
  
Führen Sie die Schritte in diesem Artikel in folgenden Fällen aus:
  
- In Ihrem Unternehmen befinden sich Benutzer in verschiedenen Domänen. Beispiel: Rob@ContosoEast.com und Ann@ContosoWest.com.

- Sie möchten den Personen in Ihrer Organisation die Möglichkeit geben, Skype for Business zu verwenden, um Personen in bestimmten Unternehmen außerhalb Ihrer Organisation zu kontaktieren.

- Sie möchten, dass alle anderen Personen auf der Welt, Skype for Business Sie über Ihre E-Mail-Adresse finden und Kontakt zu Ihnen aufnehmen können. Wenn Sie und die anderen Benutzer die Standardeinstellungen für Skype for Business verwenden, funktioniert dies automatisch. Anderenfalls müssen sie sicherstellen, dass Ihre Domäne nicht durch ihre Konfiguration blockiert wird.

## <a name="enable-business-to-business-communications-for-your-users"></a>Aktivieren der Business-to-Business-Kommunikation für die Benutzer

<a name="bk_preview"> </a>

Sie müssen in [beiden Organisationen über](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) Administratorberechtigungen Microsoft 365 oder Office 365 für diese Kommunikation verfügen.

![Ein Symbol mit dem Microsoft Teams Logo.](../images/teams-logo-30x30.png) **Verwenden des Teams Admin Centers**
  
1. Melden Sie sich mit Ihrem Microsoft 365 Oder Office 365 Administratorkonto an.

2. Wechseln Sie im Admin Center zu **Admin Center**  >  **Teams.**

    ![Wählen Sie den Teams aus.](../images/MS-Teams-Admin.png)
  
3. Wählen Sie **Teams In der Mitte** die Option **Skype** > **Legacy-Portal** Wählen Sie das 
  ![ SfB-Legacyportal aus.](../images/SFBlegacy-size65.png)

4. Wählen Sie unter **Skype for Business Admin Center** die Option **Organisation** > **Externe Kommunikation** aus.
5. Um die Kommunikation mit einem bestimmten Unternehmen oder mit Benutzern in einer anderen Domäne einzurichten, wählen Sie im Dropdownfeld **Nur für zulässige Domänen aktivieren**.

    ODER wählen Sie, wenn Sie die Kommunikation mit allen anderen Unternehmen aktivieren möchten, die über offene Skype for Business-Richtlinien verfügen, die Option **Aktivieren mit Ausnahme der blockierten Domänen** aus. Dies ist die Standardeinstellung.

6. Wählen **Sie unter Blockierte oder zulässige Domänen** den Namen der Domäne aus, die Sie zulassen **+** möchten, und fügen Sie diesen hinzu.

7. Stellen Sie sicher, dass der Administrator in der anderen Organisation die gleichen Schritte in seiner Skype for Business **Admin Center führt.** Beispiel: In der Liste der **zugelassenen Domänen** muss der Administrator der anderen Organisation die Domäne für Ihr Unternehmen eingeben.

8. Wenn Sie die Windows-Firewall verwenden, öffnet Skype for Business die erforderlichen Ports automatisch.

    Wenn Ihre Organisation die Internetverbindung von Computern in Ihrem Netzwerk mit einer anderen Firewall-Lösung einschränkt, vergewissern Sie sich, dass Ihre Clientcomputer auf die folgenden [URLs und IP-Adressbereiche von Office 365](/microsoftteams/office-365-urls-ip-address-ranges) zugreifen können. Dies kann das Hinzufügen der FQDNs zur Liste der zulässigen ausgehenden Verbindungen in Ihrer Firewall- oder Proxyinfrastrukturkonfiguration erfordern: **\* api.skype.com,** \* *_users.storage.live.com_* und **graph.skype.com**. Anweisungen zum Öffnen dieser Ports in Ihrer Firewall finden Sie in der Dokumentation zum Port.

    Eine Liste aller Ports, die Sie öffnen müssen, finden Sie unter Office 365 [URLs und IP-Adressbereiche.](/microsoftteams/office-365-urls-ip-address-ranges)

9. Stellen Sie sicher, dass der Administrator in der Organisation diese Schritte ebenfalls befolgt hat.

10. **WARTEN SIE MIT DEM TEST BIS ZU 24 STUNDEN**. Wenn Sie die Einstellungen für externe Kommunikation ändern, kann es bis zu 24 Stunden dauern, bis die Änderungen in allen Rechenzentren auffüllen.

![Skype.](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Sie können Ihren Benutzern erlauben, nach allen Personen zu suchen und mit ihnen zu Skype, der kostenlosen Verbraucher-App! Weitere Informationen finden Sie unter [Skype for Business hinzufügen von Skype Kontakten.](let-skype-for-business-users-add-skype-contacts.md)
  
## <a name="test-and-troubleshoot"></a>Tests und Problembehandlung

<a name="bk_preview"> </a>

 **Am häufigsten haben Benutzer beim Einrichten der Kommunikation zwischen Unternehmen Probleme damit, die [URLs und IP-Adressbereiche von Office 365](/microsoftteams/office-365-urls-ip-address-ranges) richtig festzulegen.**
  
Um Ihr Setup zu testen, benötigen Sie einen Kontakt in Skype for Business, der sich nicht hinter der Firewall Ihrer Firma befindet.
  
1. Warten Sie nach einer Änderung der Einstellungen für externe Kommunikation **BIS ZU 24 STUNDEN, BEVOR SIE TESTS DURCHFÜHREN**.

2. Suchen Sie in Skype for Business nach Ihrem Kontakt in Skype for Business, und senden Sie eine Chatanfrage.

    Wenn Sie eine Meldung erhalten, dass die Nachricht aufgrund einer Unternehmensrichtlinie nicht gesendet werden konnte, müssen Sie Ihre Office 365 URLs und [IP-Adressbereiche überprüfen.](/microsoftteams/office-365-urls-ip-address-ranges)

3. Bitten Sie Ihren Skype for Business-Kontakt, Ihnen eine Chatanfrage zu senden. Wenn Sie die Anfrage nicht erhalten, stellen die Firewalleinstellungen das Problem dar (dabei wird angenommen, dass der Kontakt bereits die Richtigkeit seiner Firewalleinstellungen überprüft hat).

4. Eine weitere Möglichkeit, um zu testen, ob die Firewall das Problem darstellt, besteht in einem Ort mit WLAN, der sich nicht hinter Ihrer Firewall befindet, z. B. in einem Café. Verwenden Skype for Business, um eine Chatanfrage an Ihren Kontakt zu senden. Wenn die Nachricht dort gesendet wird, an Ihrem Arbeitsplatz aber nicht, wissen Sie, dass die Firewall das Problem darstellt.

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Beim Herstellen einer Verbindung mit einem anderen Unternehmen andere Personen finden und selbst gefunden werden

<a name="bk_preview"> </a>

Nachdem Sie die externe Kommunikation mit anderen Skype for Business Benutzern aktiviert haben, können die Benutzer Partnerbenutzer Skype for Business, indem sie nach ihren Anmeldenamen suchen. Beispiel: Rob@contoso.com. Anschließend müssen sie die Person zu ihrer Kontaktliste hinzufügen.
  
![Um einen Benutzer in einem Partnerunternehmen zu finden, müssen Sie nach seiner E-Mail-Adresse suchen (dies ist normalerweise auch der Anmeldename).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Tipps zum Einrichten der Kommunikation mit Partnerunternehmen

<a name="bk_preview"> </a>

- Informationen zum Konfigurieren des Verbunds zwischen Skype for Business 2015 und Skype for Business Online finden Sie in diesem Artikel: Konfigurieren des Verbunds [mit Skype for Business Online.](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)

- Informationen zum Konfigurieren des Verbunds zwischen Lync und Skype for Business Online finden Sie in diesem Artikel: Konfigurieren der Unterstützung für einen Verbund für [einen Lync Online-Kunden.](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer)

- Wenn zwei Skype for Business-Benutzer in Microsoft 365 oder Office 365 in getrennten Domänen miteinander kommunizieren, können sie nur Skype for Business-Features (z. B. Videounterhaltungen oder Desktopfreigabe) verwenden, die in beiden Organisationen aktiviert sind.

- Wenn für einen Skype for Business-Benutzer in Ihrer Organisation ein In-Place- oder Einsicherungsverfahren aktiviert wird, werden alle Chatunterhaltungen zwischen diesem Benutzer und anderen Skype for Business- oder Skype-Benutzern **in** wiederherstellbare Elemente in ihrem Postfach gespeichert. Diese Unterhaltungen werden nicht im Ordner **Aufgezeichnete Unterhaltungen** in ihrem Postfach gespeichert.

## <a name="turn-off-external-communication-for-specific-individuals"></a>Externe Kommunikation für bestimmte Personen deaktivieren

<a name="bk_preview"> </a>

Nachdem Sie die externe Kommunikation für Ihr gesamtes Unternehmen aktiviert haben, können Sie sie für bestimmte Personen deaktivieren.
  
1. Melden Sie sich mit Ihrem Microsoft 365 Oder Office 365 Administratorkonto an.

2. Wechseln Sie im Admin Center zu **Aktive**  >  **Benutzer**.

3. Klicken Sie in der Liste der Benutzer auf den Benutzer und dann unter **Weitere Einstellungen** auf **Skype for Business-Eigenschaften bearbeiten**.

    ![Wählen Sie Skype for Business aus.](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. Wählen Sie **Skype for Business Admin Center** die Option Externe Kommunikation **aus.**

    Auf der **Seite** Optionen sind alle Optionen ausgewählt. Löschen Sie die Kommunikationen, die Sie deaktivieren möchten. Die folgende Abbildung zeigt, dass Jakob mit Personen in anderen vertrauenswürdigen Unternehmen kommunizieren kann, darüber hinaus jedoch nicht mit anderen Skype-Nutzern.

    ![Wählen Sie Externe Kontakte aus.](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Klicken Sie auf **Speichern**.

> [!NOTE]
> Sie müssen ggf. bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Verwandte Themen

<a name="bk_preview"> </a>

[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)
  
[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)
