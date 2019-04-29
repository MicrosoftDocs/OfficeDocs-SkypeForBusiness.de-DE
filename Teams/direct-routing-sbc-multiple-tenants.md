---
title: Konfigurieren eines Session Border Controllers für mehrere Mandanten
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Informationen Sie zum Konfigurieren einer Session Border Controller (SBC), um mehrere Mandanten zu verarbeiten.
ms.openlocfilehash: 5338046724cc3768929b41dceb060aec1cee0bd6
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401488"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Konfigurieren eines Session Border Controllers für mehrere Mandanten

Direktes Routing unterstützt Konfigurieren einer Session Border Controller (SBC), um mehrere Mandanten zu verarbeiten.

> [!NOTE]
> In diesem Szenario dient zur Microsoft-Partnern und/oder PSTN Netzbetreibern, die als Netzbetreiber weiter unten in diesem Dokument bezeichnet. Ein Netzbetreiber verkauft Telefoniediensten an Microsoft-Teams, ihren Kunden übermittelt. 

Ein Netzbetreiber:
- Wird bereitgestellt und verwaltet einen SBC im Rechenzentrum (Benutzer müssen sich nicht um einen SBC zu implementieren und sie erhalten Telefoniediensten aus der Netzbetreiber im Teams-Client).
- Sind den SBC für mehrere Mandanten.
- Bietet Services PSTN Kunden.
- Verwaltet die Anrufqualität Ende zu Ende.
- Gebühren separat für PSTN-Dienste.

Netzbetreiber wird nicht von Microsoft verwaltet werden. Microsoft bietet eine Nebenstellenanlage (Microsoft Telefonsystem) und einem Client Teams, Telefone zertifiziert und zertifiziert SBCs, die in der Microsoft-Telefonsystem verwendet werden können. Bevor Sie einen Netzbetreiber auswählen, stellen Sie sicher, dass Ihrer Wahl über eine zertifizierten SBC und Sprachqualität Ende zum Verwalten kann.

Es folgen die technischen Implementierungsschritte zum Konfigurieren der Szenarios.

**Netzbetreiber:**
1. Bereitstellen Sie den SBC, und konfigurieren sie für das hosting Szenario gemäß den [Anweisungen der zertifizierten SBC-Anbieter](#deploy-and-configure-the-sbc).
2. Registrieren Sie einer Benutzerbasis-Domänenname in den Mandanten Netzbetreiber und fordern Sie ein Platzhalterzertifikat an.
3. Registrieren Sie eine Unterdomäne für jeden Kunden, die Teil der Basis Domäne ist.

**Netzbetreiber mit Kunden globaler Administrator:**
1. Hinzufügen der Unterdomäne Name, die dem Kunden-Mandanten.
2. Der Name der Unterdomäne zu aktivieren.
3. Konfigurieren Sie den Trunk aus der Netzbetreiber Benutzern Kunden Mandanten und bereitgestellt werden soll.

*Stellen Sie sicher, dass Sie die Grundlagen von DNS und Verwaltung von der Domänennamen in Office 365 kennen. Überprüfen Sie vor dem Fortsetzen des Vorgangs [Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*

## <a name="deploy-and-configure-the-sbc"></a>Bereitstellen Sie und konfigurieren Sie den SBC

Die detaillierte Schritte zum Bereitstellen und SBCs für einen SBC-hosting-Szenario konfigurieren finden Sie in den SBC Herstellers.

- **AudioCodes:** [Direkte Routingkonfiguration Notizen](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), die Konfiguration von den SBC Hosten in "Connecting AudioCodes SBC zu Microsoft-Teams, direkte Routing Hosting-Modell Konfiguration Notiz" beschriebenen Szenario 
- **Des Menübands Communications:**  Finden Sie im [Menüband Communications SBC Core Microsoft Teams Konfigurationshandbuch](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) Dokumentation zum Menüband Core Datenreihe SBCs zu konfigurieren und zu dieser Seite [Menüband Best Practice - Konfigurieren von Netzbetreibern für Microsoft-Teams direkte Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)

> [!NOTE]
> Bitte achten Sie auf die Kopfzeile "Kontakt" zu konfigurieren. Die Kontakt Kopfzeile wird verwendet, um den Mandanten Kunden auf eingehende Invite-Nachricht zu suchen. 

## <a name="register-a-base-domain-and-subdomains"></a>Registrieren einer Basis Domäne und Unterdomänen

Sie müssen für das hosting-Szenario erstellen:
- Eine Benutzerbasis-Domänenname Besitz der Netzbetreiber.
- Eine untergeordnete Domäne, die Bestandteil der Benutzerbasis-Domänenname in jeder Mandant des Kunden ist.

Im folgenden Beispiel:
- Adatum ist einem Netzbetreiber abgeschlossen, die mehrere Privatkunden durch Bereitstellen von Diensten für Internet- und Telefonie.
- Woodgrove Bank, Contoso und Adventure Works sind drei Kunden, die Office 365-Domänen, aber die Telefondienste von Adatum empfangen.

Unterdomänen **müssen** entsprechen den Vollqualifizierten Domänennamen des Trunks, die beim Senden der Einladung zu Office 365 für den Kunden und den FQDN in der Kopfzeile Kontakt konfiguriert werden. 

Wenn ein Anruf an den Office 365 direkten Routing-Schnittstelle ankommt, verwendet die Schnittstelle die Kopfzeile des Kontakts, um den Mandanten zu erhalten, in dem der Benutzer gesucht werden soll. Direktes Routing wird nicht verwendet, Nachschlagen Telefon auf einladen, wie einige Kunden möglicherweise nicht-DID-Nummern, die in mehreren Mandanten überlappen können. Aus diesem Grund ist der FQDN in der Kopfzeile des Kontakts erforderlich identifiziert den genauen Mandanten zum Nachschlagen von der Benutzer von der Telefonnummer.

*Weitere Informationen zum Erstellen von Domänennamen in Office 365-Mandanten [Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) überprüfen.*

Im folgende Diagramm sind die Anforderungen zur Basis Domäne, untergeordnete Domänen und Kontakt Kopfzeile zusammengefasst.

![Anforderungen zu grundlegenden Unterdomänen und Contact-header](media/direct-routing-1-sbc-requirements.png)

Der SBC erfordert ein Zertifikat aus, um die Verbindungen zu authentifizieren. Für das hosting SBC-Szenario muss der Netzbetreiber zum Anfordern eines Zertifikats mit SAN * \*.base_domain (beispielsweise \*customers.adatum.biz)*. Dieses Zertifikat kann verwendet werden, um Verbindungen für mehrere Mandanten aus einer einzelnen SBC bedient zu authentifizieren.

In der folgenden Tabelle ist ein Beispiel für eine Konfiguration.


|Name der neuen Domäne |Typ|Registriert  |Zertifikat für SBC SAN  |Mandanten Standarddomäne im Beispiel  |FQDN ein, der in der Kopfzeile des Kontakts SBC präsentieren muss, wenn Anrufe an Benutzer senden|
|---------|---------|---------|---------|---------|---------|
|Customers.adatum.biz|    Base     |     In Netzbetreiber Mandanten  |    \*. customers.adatum.biz  |   adatum.biz      |NA, handelt es sich um einen Dienst Mandanten, keine Benutzer |
|sbc1.Customers.adatum.biz|    Unterdomäne  |    In einem Mandanten Kunden  |    \*. customers.adatum.biz  | woodgrovebank.US  |  sbc1.Customers.adatum.biz|
|sbc2.Customers.adatum.biz  |   Unterdomäne | In einem Mandanten Kunden   |   \*. customers.adatum.biz   |contoso.com   |sbc2.Customers.adatum.biz |
|SBC3.Customers.adatum.biz |   Unterdomäne | In einem Mandanten Kunden |   \*. customers.adatum.biz  |  AdventureWorks.com | SBC3.Customers.adatum.biz |
||         |         |         |         |         |

Um die Base und Unterdomänen zu konfigurieren, führen Sie die unten beschriebenen Schritte ausführen. Im Beispiel wird eine Benutzerbasis-Domänenname (customers.adatum.biz) und eine Unterdomäne für einen bestimmten Kunden (sbc1.customers.adatum.biz in Woodgrove Bank-Mandanten) konfiguriert.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registrieren Sie eine Benutzerbasis-Domänenname in den Mandanten Netzbetreiber

**Diese Aktionen werden in den Mandanten Netzbetreiber ausgeführt.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Stellen Sie sicher, dass Sie den Mandanten Netzbetreiber erforderlichen Berechtigungen verfügen

Sie können nur neue Domänen hinzufügen, wenn Sie Office 365 Admin Center als ein globaler Administrator angemeldet. 

Um Ihnen die Rolle zu überprüfen, melden Sie sich der Microsoft-365-Verwaltungskonsole (https://portal.office.com), fahren Sie mit der **Benutzer** > **Aktive Benutzer**, und stellen Sie sicher, dass Sie eine globalen Administratorrolle verfügen. 

Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Office 365 finden Sie unter [Informationen zu Office 365-Administratorrollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Hinzufügen einer Basis Domäne, die dem Mandanten, und bestätigen Sie es

1.  Wechseln Sie in das Microsoft 365 Administrationscenter zu **Setup** > **Domänen** > **Domäne hinzufügen**.
2.  Geben Sie den FQDN der Basis-Domäne, in das Feld **Geben Sie eine Domäne, die Sie besitzen** . Im folgenden Beispiel wird die Basiskalender Domäne *customers.adatum.biz*.

    ![Hinzufügen einer Basis Domäne](media/direct-routing-2-sbc-add-domain.png)

3. Klicken Sie auf **Weiter**.
4. Im Beispiel hat der Mandanten adatum.biz bereits als Namen einer überprüften Domäne. Der Assistent fordert nicht für eine zusätzliche Überprüfung, da customers.adatum.biz eine Unterdomäne für den Namen bereits registriert ist. Wenn Sie einen vollqualifizierten Domänennamen, der nicht hinzufügen vor überprüft wurde, müssen Sie über den Prozess der Überprüfung geleitet. Die Überprüfung wird [unten beschriebenen](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

    ![Bestätigung des einen Namen für die überprüften Domäne](media/direct-routing-3-sbc-verify-domain.png)

5.  Klicken Sie auf **Weiter**, und wählen Sie auf der Seite **Einstellungen für DNS-Updates** **ich fügen die DNS-Datensätze selbst** , und klicken Sie auf **Weiter**.
6.  Deaktivieren Sie auf der nächsten Seite alle Werte (es sei denn, Sie den Domänennamen für Exchange, SharePoint oder Teams/Skype für Unternehmen verwenden möchten), klicken Sie auf **Weiter**, und klicken Sie dann auf **Fertig stellen**. Stellen Sie sicher, dass die neue Domäne im Status Setup abgeschlossen ist.

    ![Domänen mit dem Status der Installation abgeschlossen](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>Aktivieren Sie den Domänennamen

Nachdem Sie einen Domänennamen registriert haben, Sie es aktivieren, indem Sie mindestens eine E1, E3, hinzufügen müssen oder E5 lizenziert Adresse Benutzer- und Zuweisen einer SIP-Adresse mit dem FQDN Teil der SIP die erstellte Basiskalender Domäne entsprechen. 

*Weitere Informationen zum Hinzufügen von Benutzern in Office 365-Mandanten [Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) überprüfen.*

Beispiel: test@customers.adatum.biz

![Die Aktivierungsseite Basis Domäne](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrieren Sie einen Unterdomänennamen in einem Mandanten Kunden

Sie müssen eine eindeutige Unterdomänennamen für jeden Kunden zu erstellen. In diesem Beispiel erstellen wir eine Unterdomäne sbc1.customers.adatum.biz in einem Mandanten mit der standardmäßigen Domain Name woodgrovebank.us.

**Alle nachfolgenden Aktionen sind in den Kunden-Mandanten.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Stellen Sie sicher, dass Sie den Mandanten Kunden erforderlichen Berechtigungen verfügen

Sie können nur neue Domänen hinzufügen, wenn Sie Office 365 Admin Center als ein globaler Administrator angemeldet. 

Um Ihnen die Rolle zu überprüfen, melden Sie sich der Microsoft-365-Verwaltungskonsole (https://portal.office.com), fahren Sie mit der **Benutzer** > **Aktive Benutzer**, und stellen Sie sicher, dass Sie eine globalen Administratorrolle verfügen. 

Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Office 365 finden Sie unter [Informationen zu Office 365-Administratorrollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Den Mandanten Kunden eine Unterdomäne hinzu, und bestätigen Sie es
1. Wechseln Sie in das Microsoft 365 Administrationscenter zu **Setup** > **Domänen** > **Domäne hinzufügen**.
2. Geben Sie den FQDN des die Unterdomäne für diesen Mandanten, in das Feld **Geben Sie eine Domäne, die Sie besitzen** . Im folgenden Beispiel wird die Unterdomäne sbc1.customers.adatum.biz.

    ![Hinzufügen einer Unterdomäne Kunden](media/direct-routing-5-sbc-add-customer-domain.png)

3. Klicken Sie auf **Weiter**.
4. Der FQDN wurde im Mandanten noch nie registriert. Im nächsten Schritt müssen Sie die Domäne überprüfen. Wählen Sie aus, **Fügen Sie stattdessen eine TXT-Eintrag hinzu**. 

    ![Optionen auf der Seite Domäne überprüfen](media/direct-routing-6-sbc-verify-customer-domain.png)

5. Klicken Sie auf **Weiter**, und notieren Sie den TXT-Wert generiert, um den Domänennamen zu überprüfen.

    ![Textdatensätze auf der Seite Domäne überprüfen](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Erstellen der TXT-Eintrag mit dem Wert aus dem vorherigen Schritt im DNS-Hostinganbieter des Mobilfunkbetreibers.

    ![Erstellen der TXT-Eintrag in der Netzbetreiber DNS-Hostinganbieter](media/direct-routing-8-sbc-txt-record.png)

    Weitere Informationen finden Sie in [Erstellen von DNS-Datensätze an alle DNS-Hostinganbieter für Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Gehen Sie zurück zu der Kunde Microsoft 365 Administrationscenter, und klicken Sie auf **Überprüfen**. 
8. Klicken Sie auf der nächsten Seite Wählen Sie **ich werde die DNS-Datensätze selbst hinzufügen** , und klicken Sie auf **Weiter**.

    ![Optionen auf der Seite Update DNS-Einstellungen](media/direct-routing-9-sbc-update-dns.png)

9. Klicken Sie auf der Seite **Wählen Sie Ihre online-Dienste** deaktivieren Sie alle Optionen, und klicken Sie auf **Weiter**.

    ![Wählen Sie die online-Dienste-Seite](media/direct-routing-10-sbc-choose-services.png)

10. Klicken Sie auf der Seite **Update DNS-Einstellungen** auf **Fertig stellen** .

    ![Seite Update DNS-Einstellungen](media/direct-routing-11-sbc-update-dns-finish.png)

11. Stellen Sie sicher, dass der Status **Setup abgeschlossen**ist. 
    
    ![Seite Status von Setup vollständig anzeigen](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a>Aktivieren Sie den Unterdomänennamen

Nachdem Sie einen Domänennamen registrieren, müssen Sie mindestens einen Benutzer hinzufügen zu aktivieren, und weisen Sie eine SIP-Adresse mit dem FQDN-Abschnitt, der die SIP-Adresse die erstellte Unterdomäne im Customer Mandanten übereinstimmenden.

*Weitere Informationen zum Hinzufügen von Benutzern in Office 365-Mandanten [Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) überprüfen.*

Beispiel: test@sbc1.customers.adatum.biz

![Aktivierung von der Seite Unterdomäne](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Erstellen Sie einen Benutzer Trunk und bereitgestellt werden soll

> [!NOTE]
> Basierend auf Feedback, die wir in der technischen Akzeptanzprogramm erhalten haben, kann den Vorgang des Erstellens Trunks in der Customer-Mandanten vereinfacht das Microsoft ändern. Sehen Sie sich den Dokumentationsupdates auf dieser Seite, und führen Sie die Microsoft technischen Communityblogs für Weitere Informationen. 

Erstellen Sie einen Trunk in der Customer-Domäne mit dem Befehl New-CSonlinePSTNGateway. Der Trunk FQDN **muss** übereinstimmen, die Unterdomäne für den Kunden erstellt wird.

Beispiel:

```
New-CSOnlinePSTNGateway –FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068
```

Wenn Sie den Trunk zu erstellen, wird möglicherweise die folgende Fehlermeldung angezeigt:

```
Can not use the "sbc1.customers.adatum.biz" domain as it was not configured for this tenant.
```

Warten Sie einige Zeit für die Domäne Registrierung und Aktivierung replizieren, und versuchen Sie es erneut.

Bereitstellung von Benutzern mit den Telefonnummern, und konfigurieren Sie VoIP-routing.

Weitere Informationen zu den New-CSOnlinePSTNGateway finden Sie Einrichten von Benutzern und Konfigurieren von VoIP-routing, zum [Direkten Routing konfigurieren](direct-routing-configure.md).


Finden Sie in den [SBC Hersteller Anweisungen](#deploy-and-configure-the-sbc) zum Konfigurieren von den Vollqualifizierten Domänennamen Unterdomänen in der Kopfzeile Kontakt gesendet.

