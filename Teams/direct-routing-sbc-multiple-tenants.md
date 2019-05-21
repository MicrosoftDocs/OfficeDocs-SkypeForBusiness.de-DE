---
title: Konfigurieren eines Session Border Controllers für mehrere Mandanten
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Hier erfahren Sie, wie Sie einen SBC (Session Border Controller) für die Bereitstellung mehrerer Mandanten konfigurieren.
ms.openlocfilehash: 5392359307d97e010f86d3bb71f2f7c3f3d1ffb6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290469"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Konfigurieren eines Session Border Controllers für mehrere Mandanten

Das direkte Routing unterstützt die Konfiguration eines SBC (Session Border Controller) für die Bereitstellung mehrerer Mandanten.

> [!NOTE]
> Dieses Szenario wurde für Microsoft-Partner und/oder PSTN-Netzbetreiber entwickelt, die später in diesem Dokument als Carrier bezeichnet werden. Ein Netzbetreiber verkauft Telefondienste, die an Microsoft Teams an Ihre Kunden ausgeliefert werden. 

Ein Netzbetreiber:
- Bereitstellung und Verwaltung eines SBC in seinem Rechenzentrum (Kunden müssen keinen SBC implementieren, und Sie erhalten Telefonie-Services vom Netzbetreiber im Teams-Client).
- Verbindet den SBC mit mehreren Mandanten.
- Bietet Kunden PSTN-Dienste.
- Verwaltet die Anrufqualität Ende bis Ende.
- Gebühren separat für PSTN-Dienste.

Microsoft verwaltet keine Netzbetreiber. Microsoft bietet eine Telefonanlage (Microsoft Phone System) und einen Teams-Client, bescheinigt Telefone und bescheinigt SBCS, die mit dem Microsoft-Telefonsystem verwendet werden können. Bevor Sie einen Netzbetreiber auswählen, stellen Sie bitte sicher, dass Ihre Wahl über einen zertifizierten SBC verfügt und die Sprachqualität bis zum Ende verwalten kann.

Im folgenden finden Sie die Schritte zur technischen Implementierung zum Konfigurieren des Szenarios.

**Nur Netzbetreiber:**
1. Stellen Sie den SBC bereit, und konfigurieren Sie ihn für das Hosting-Szenario gemäß den [Anweisungen der Certified SBC-Anbieter](#deploy-and-configure-the-sbc).
2. Registrieren Sie einen Basisdomänen Namen im Carrier-Mandanten, und fordern Sie ein Platzhalterzertifikat an.
3. Registrieren Sie eine Unterdomäne für jeden Kunden, der Teil der Basisdomäne ist.

**Netzbetreiber mit einem globalen Kunden Administrator:**
1. Fügen Sie den Namen der Unterdomäne dem Kundenmandanten hinzu.
2. Aktivieren Sie den Namen der Unterdomäne.
3. Konfigurieren Sie den trunk vom Netzbetreiber zum Kundenmandanten und Bereitstellen von Benutzern.

*Stellen Sie bitte sicher, dass Sie die DNS-Grundlagen kennen und wissen, wie der Domänenname in Office 365 verwaltet wird. Überprüfen [Sie, wie Sie Hilfe zu Office 365-Domänen erhalten](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) , bevor Sie fortfahren.*

## <a name="deploy-and-configure-the-sbc"></a>Bereitstellen und Konfigurieren des SBC

Die detaillierten Schritte zum Bereitstellen und Konfigurieren von SBCS für ein SBC-Hosting-Szenario finden Sie in der Dokumentation des SBC-Anbieters.

- **AudioCodes:** [Direct Routing-Konfigurationshinweise](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), die Konfiguration des SBC-Host Szenarios, das unter "Verbinden von AudioCodes SBC mit Microsoft Teams Direct Routing Hosting Model Configuration Note" beschrieben wird. 
- **Band Kommunikation:**  Weitere Informationen finden Sie im [Menüband Communications SBC Core Microsoft Teams-Konfigurationshandbuch](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) für die Dokumentation zur Konfiguration der Menüband-Core-Serie SBCS und zu diesem Seiten [Menüband bewährte Methode – Konfigurieren von Netzbetreibern für Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)

> [!NOTE]
> Bitte achten Sie darauf, wie Sie die Kopfzeile "Kontakt" konfigurieren. Der Kontakt Kopf wird verwendet, um den Kundenmandanten in der eingehenden Einladungsnachricht zu finden. 

## <a name="register-a-base-domain-and-subdomains"></a>Registrieren einer Basisdomäne und Unterdomänen

Für das Hosting-Szenario müssen Sie Folgendes erstellen:
- Ein Basisdomänenname im Besitz des Netzbetreibers.
- Eine Unterdomäne, die Teil des Basisdomänen namens in jedem Kundenmandanten ist.

Im folgenden Beispiel:
- Adatum ist ein Carrier, der mehreren Kunden dient, indem es Internet-und Telefonie-Dienste bereitstellt.
- Woodgrove Bank, Contoso und Adventure Works sind drei Kunden, die über Office 365-Domänen verfügen, aber die Telefonie-Services von Adatum erhalten.

Unterdomänen **müssen** mit dem FQDN-Namen des Trunks übereinstimmen, der für den Kunden konfiguriert wird, und dem FQDN in der Kontakt Kopfzeile, wenn Sie die Einladung zu Office 365 senden. 

Wenn ein Anruf an der Office 365 Direct-Routing Schnittstelle eingeht, verwendet die Schnittstelle die Kontakt Kopfzeile, um den Mandanten zu finden, in dem der Benutzer nachgeschlagen werden soll. Bei der direkten Weiterleitung wird keine telefonnummernsuche auf der Einladung verwendet, da einige Kunden möglicherweise nicht-DID-Nummern haben, die sich in mehreren Mandanten überlappen können. Daher ist der FQDN-Name in der Kopfzeile des Kontakts erforderlich, um den genauen Mandanten zu identifizieren, um den Benutzer anhand der Telefonnummer nachschlagen zu können.

*Weitere Informationen zum Erstellen von Domänennamen in Office 365-Mandanten finden Sie [unter Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*

Das folgende Diagramm fasst die Anforderungen für Basisdomänen, Unterdomänen und Kontakt Kopfzeilen zusammen.

![Anforderungen für die Basisdomäne, Unterdomänen und Kontakt Kopfzeile](media/direct-routing-1-sbc-requirements.png)

Für den SBC ist ein Zertifikat erforderlich, um die Verbindungen zu authentifizieren. Für das SBC-Hosting-Szenario muss der Netzbetreiber ein Zertifikat mit San * \*. base_domain (beispielsweise \*Customers.adatum.biz)* anfordern. Dieses Zertifikat kann verwendet werden, um Verbindungen mit mehreren Mandanten zu authentifizieren, die über einen einzelnen SBC bedient werden.

Die folgende Tabelle zeigt ein Beispiel für eine Konfiguration.


|Neuer Domänenname |Typ|Registriert  |Zertifikat-San für SBC  |Standarddomäne des Mandanten im Beispiel  |FQDN-Name, den SBC beim Senden von Anrufen an Benutzer in der Kontakt Kopfzeile vorlegen muss|
|---------|---------|---------|---------|---------|---------|
|Customers.adatum.biz|    Basis     |     In Carrier-Mandant  |    \*. Customers.adatum.biz  |   adatum.biz      |Na, dies ist ein Dienst Mandant, keine Benutzer |
|sbc1.Customers.adatum.biz|    Subdomain  |    In einem Kundenmandanten  |    \*. Customers.adatum.biz  | woodgrovebank.US  |  sbc1.Customers.adatum.biz|
|sbc2.Customers.adatum.biz  |   Subdomain | In einem Kundenmandanten   |   \*. Customers.adatum.biz   |contoso.com   |sbc2.Customers.adatum.biz |
|sbc3.Customers.adatum.biz |   Subdomain | In einem Kundenmandanten |   \*. Customers.adatum.biz  |  AdventureWorks.com | sbc3.Customers.adatum.biz |
||         |         |         |         |         |

Führen Sie die nachstehenden Schritte aus, um die Basis-und Subdomänen zu konfigurieren. Im Beispiel konfigurieren wir einen Basisdomänen Namen (Customers.adatum.biz) und eine Unterdomäne für einen Kunden (sbc1.Customers.adatum.biz in Woodgrove Bank-Mandanten).

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registrieren eines Basisdomänen namens im Carrier-Mandanten

**Diese Aktionen werden beim Mandanten des Netzbetreibers ausgeführt.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Stellen Sie sicher, dass Sie über die erforderlichen Rechte im Anbieter Mandanten verfügen

Wenn Sie sich beim Microsoft 365 Admin Center als globaler Administrator angemeldet haben, können Sie nur neue Domänen hinzufügen. 

Um die Rolle zu überprüfen, die Sie haben, melden Sie sich bitte beim Microsofthttps://portal.office.com)365 Admin Center **** > an (wechseln Sie zu**aktive**Benutzer von Benutzern, und überprüfen Sie, ob Sie über eine globale Administrator Rolle verfügen. 

Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Office 365 finden Sie unter Informationen zu [Office 365-Administratorrollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Dem Mandanten eine Basisdomäne hinzufügen und diese überprüfen

1.  Wechseln Sie im Microsoft 365 Admin Center zu **Setup** > **Domains** > **Domain hinzufügen**.
2.  Geben Sie im Feld Ihre **eigene Domäne eingeben** den FQDN der Basisdomäne ein. Im folgenden Beispiel ist die Basisdomäne *Customers.adatum.biz*.

    ![Hinzufügen einer Basisdomäne](media/direct-routing-2-sbc-add-domain.png)

3. Klicken Sie auf **Weiter**.
4. Im Beispiel hat der Mandant bereits adatum.biz als bestätigten Domänennamen. Der Assistent fragt keine zusätzliche Überprüfung ab, da Customers.adatum.biz eine Unterdomäne für den bereits registrierten Namen ist. Wenn Sie jedoch einen FQDN hinzufügen, der noch nicht überprüft wurde, müssen Sie den Verifizierungsprozess durchlaufen. Der Verifizierungsprozess wird im [folgenden beschrieben](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

    ![Bestätigung eines bestätigten Domänennamens](media/direct-routing-3-sbc-verify-domain.png)

5.  Klicken Sie auf **weiter**, und wählen Sie auf der Seite **DNS-Einstellungen aktualisieren** die Option **Ich möchte die DNS-Einträge selbst hinzufügen** aus, und klicken Sie auf **weiter**.
6.  Deaktivieren Sie auf der nächsten Seite alle Werte (es sei denn, Sie möchten den Domänennamen für Exchange, SharePoint oder Teams/Skype for Business verwenden), klicken Sie auf **weiter**, und klicken Sie dann auf **Fertig stellen**. Stellen Sie sicher, dass sich Ihre neue Domäne im Status "Setup abgeschlossen" befindet.

    ![Domänen mit dem Status "Setup abgeschlossen"](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>Aktivieren des Domänennamens

Nachdem Sie einen Domänennamen registriert haben, müssen Sie ihn aktivieren, indem Sie mindestens einen von E1, E3 oder E5 lizenzierten Benutzer hinzufügen und dem FQDN-Teil der SIP-Adresse, die der erstellten Basisdomäne entspricht, eine SIP-Adresse zuweisen. 

*Weitere Informationen zum Hinzufügen von Benutzern in Office 365-Mandanten finden Sie [unter Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*

Beispiel: Test@Customers.adatum.biz

![Seite "Basisdomänen Aktivierung"](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrieren eines Unterdomänen namens in einem Kundenmandanten

Sie müssen für jeden Kunden einen eindeutigen Subdomain-Namen erstellen. In diesem Beispiel wird eine Subdomain-sbc1.Customers.adatum.biz in einem Mandanten mit dem standardmäßigen Domänennamen woodgrovebank.US erstellt.

**Alle nachstehenden Aktionen befinden sich im Kundenmandanten.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Sicherstellen, dass Sie über die erforderlichen Rechte im Kundenmandanten verfügen

Wenn Sie sich beim Microsoft 365 Admin Center als globaler Administrator angemeldet haben, können Sie nur neue Domänen hinzufügen. 

Um die Rolle zu überprüfen, die Sie haben, melden Sie sich bitte beim Microsofthttps://portal.office.com)365 Admin Center **** > an (wechseln Sie zu**aktive**Benutzer von Benutzern, und überprüfen Sie, ob Sie über eine globale Administrator Rolle verfügen. 

Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Office 365 finden Sie unter Informationen zu [Office 365-Administratorrollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Hinzufügen einer Unterdomäne zum Kundenmandanten und zur Überprüfung
1. Wechseln Sie im Microsoft 365 Admin Center zu **Setup** > **Domains** > **Domain hinzufügen**.
2. Geben Sie im Feld Ihre **eigene Domäne eingeben** den FQDN der Unterdomäne für diesen Mandanten ein. Im folgenden Beispiel ist die Unterdomäne sbc1.Customers.adatum.biz.

    ![Hinzufügen einer Kunden-Unterdomäne](media/direct-routing-5-sbc-add-customer-domain.png)

3. Klicken Sie auf **Weiter**.
4. Der FQDN wurde nie im Mandanten registriert. Im nächsten Schritt müssen Sie die Domäne überprüfen. Wählen Sie **stattdessen TXT-Eintrag hinzufügen**aus. 

    ![Optionen auf der Seite "Domäne überprüfen"](media/direct-routing-6-sbc-verify-customer-domain.png)

5. Klicken Sie auf **weiter**, und notieren Sie sich den generierten txt-Wert, um den Domänennamen zu überprüfen.

    ![Text Einträge auf der Seite "Domäne überprüfen"](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Erstellen Sie den TXT-Eintrag mit dem Wert aus dem vorherigen Schritt im DNS-Hostinganbieter des Carriers.

    ![Erstellen des txt-Eintrags im DNS-Hostinganbieter des Netzbetreibers](media/direct-routing-8-sbc-txt-record.png)

    Weitere Informationen finden Sie unter [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Wechseln Sie zurück zum Microsoft 365 Admin Center des Kunden, und klicken Sie auf **überprüfen**. 
8. Wählen Sie auf der nächsten Seite **die Option Ich füge die DNS-Einträge selbst hinzu** , und klicken Sie auf **weiter**.

    ![Optionen auf der Seite "DNS-Einstellungen aktualisieren"](media/direct-routing-9-sbc-update-dns.png)

9. Deaktivieren Sie auf der Seite **Onlinedienste auswählen** alle Optionen, und klicken Sie auf **weiter**.

    ![Seite "wählen Sie Ihre Onlinedienste aus"](media/direct-routing-10-sbc-choose-services.png)

10. Klicken Sie auf der Seite " **DNS-Einstellungen aktualisieren** " auf **Fertig stellen** .

    ![Seite "DNS-Einstellungen aktualisieren"](media/direct-routing-11-sbc-update-dns-finish.png)

11. Stellen Sie sicher, dass der Status **Setup abgeschlossen**ist. 
    
    ![Seite mit dem Status "Setup abgeschlossen"](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a>Aktivieren des Unterdomänen namens

Nachdem Sie einen Domänennamen registriert haben, müssen Sie ihn aktivieren, indem Sie mindestens einen Benutzer hinzufügen und eine SIP-Adresse mit dem FQDN-Teil der SIP-Adresse zuweisen, die der erstellten Unterdomäne im Kundenmandanten entspricht.

*Weitere Informationen zum Hinzufügen von Benutzern in Office 365-Mandanten finden Sie [unter Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*

Beispiel: Test@sbc1.Customers.adatum.biz

![Aktivierung der Subdomain-Seite](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Erstellen eines Trunks und Bereitstellen von Benutzern

> [!NOTE]
> Basierend auf dem Feedback, das wir im technischen Adoptionsprogramm erhalten haben, kann Microsoft das Verfahren zum Erstellen von Trunks in den Kundenmandanten ändern, um den Prozess zu vereinfachen. Schauen Sie sich die Dokumentationsupdates auf dieser Seite an, und folgen Sie den Blogs der Microsoft Technical Community, um weitere Informationen zu erhalten. 

Erstellen Sie einen trunk in der Kundendomäne mit dem Befehl New-CSonlinePSTNGateway. Der trunk-FQDN **muss** der für den Kunden erstellten Unterdomäne entsprechen.

Beispiel:

```
New-CSOnlinePSTNGateway –FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068
```

Beim Erstellen des Trunks wird möglicherweise die folgende Fehlermeldung angezeigt:

```
Can not use the "sbc1.customers.adatum.biz" domain as it was not configured for this tenant.
```

Bitte warten Sie, bis die Domänenregistrierung und-Aktivierung repliziert sind, und versuchen Sie es erneut.

Bereitstellen von Benutzern mit den Telefonnummern und Konfigurieren des VoIP-Routings

Weitere Informationen zu den neuen CSOnlinePSTNGateway und zur Bereitstellung von Benutzern sowie zum Konfigurieren des VoIP-Routings finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).


Lesen Sie dazu die [Anweisungen des SBC-Herstellers](#deploy-and-configure-the-sbc) zum Konfigurieren des Sendens des FQDN-namens von Unterdomänen in der Kontakt Kopfzeile.

