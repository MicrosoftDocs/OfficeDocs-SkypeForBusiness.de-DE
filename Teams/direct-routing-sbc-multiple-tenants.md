---
title: Konfigurieren des Sitzungs Grenz Controllers – mehrere Mandanten
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
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie einen Session Border Controller (SBC) für die Bereitstellung mehrerer Mandanten für Microsoft-Partner und/oder PSTN-Netzbetreiber konfigurieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 13d2dceb8cedc6e48d420619476cbf73c675785a
ms.sourcegitcommit: e618396eb8da958983668ad0884b4481e1ed7b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44021997"
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

Microsoft verwaltet keine Netzbetreiber. Microsoft bietet eine Telefonanlage (Microsoft Phone System) und einen Teams-Client. Microsoft bescheinigt auch Telefone und bescheinigt SBCS, die mit dem Microsoft-Telefon System verwendet werden können. Bevor Sie einen Netzbetreiber auswählen, stellen Sie bitte sicher, dass Ihre Wahl über einen zertifizierten SBC verfügt und die Sprachqualität bis zum Ende verwalten kann.

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

- **AudioCodes:** [Direct Routing-Konfigurationshinweise](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), die Konfiguration des SBC-Host Szenarios, das unter "Verbinden von AudioCodes SBC mit Microsoft Teams Direct Routing Hosting-Modell Konfigurationshinweis beschrieben wird." 
- **Oracle:** [Direct Routing-Konfigurationshinweise](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)die Konfiguration des SBC-Host Szenarios wird im Abschnitt "Microsoft" beschrieben. 
- **Band Kommunikation:**  Weitere Informationen finden Sie im [Menüband Communications SBC Core Microsoft Teams-Konfigurationshandbuch](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) für die Dokumentation zur Konfiguration der Menüband-Core-Serie SBCS und zu diesem Seiten [Menüband bewährte Methode – Konfigurieren von Netzbetreibern für Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)
- **Te-Systems (anynode):**  Bitte melden Sie sich auf der [te-Systems Community-Seite](https://community.te-systems.de/) an, um Dokumentationen und Beispiele zum Konfigurieren von anynode SBC für mehrere Mandanten zu erhalten.

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

*Weitere Informationen zum Erstellen von Domänennamen in Office 365-Organisationen finden Sie [unter Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*

Das folgende Diagramm fasst die Anforderungen für Basisdomänen, Unterdomänen und Kontakt Kopfzeilen zusammen.

![Diagramm mit Voraussetzungen für Domänen und Kontakt Kopfzeile](media/direct-routing-1-sbc-requirements.png)

Für den SBC ist ein Zertifikat erforderlich, um die Verbindungen zu authentifizieren. Für das SBC-Hosting-Szenario muss der Netzbetreiber ein Zertifikat mit San * \*. base_domain anfordern (Beispiel: \*. Customers.adatum.biz)*. Dieses Zertifikat kann verwendet werden, um Verbindungen mit mehreren Mandanten zu authentifizieren, die über einen einzelnen SBC bedient werden.


Die folgende Tabelle zeigt ein Beispiel für eine Konfiguration.


|Neuer Domänenname |Typ|Registriert  |Zertifikat-San für SBC  |Standarddomäne des Mandanten im Beispiel  |FQDN-Name, den SBC beim Senden von Anrufen an Benutzer in der Kontakt Kopfzeile vorlegen muss|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Basis     |     In Carrier-Mandant  |    \*. Customers.adatum.biz  |   adatum.biz      |Na, dies ist ein Dienst Mandant, keine Benutzer |
|sbc1.customers.adatum.biz|    Subdomain  |    In einem Kundenmandanten  |    \*. Customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Subdomain | In einem Kundenmandanten   |   \*. Customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Subdomain | In einem Kundenmandanten |   \*. Customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

Führen Sie die nachstehenden Schritte aus, um die Basis-und Subdomänen zu konfigurieren. Im Beispiel konfigurieren wir einen Basisdomänen Namen (Customers.adatum.biz) und eine Unterdomäne für einen Kunden (sbc1.Customers.adatum.biz in Woodgrove Bank-Mandanten).

> [!NOTE]
> Verwenden Sie sbcX.Customers.adatum.biz, um die Sprachausgabe im Mandanten Mandanten zu aktivieren.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registrieren eines Basisdomänen namens im Carrier-Mandanten

**Diese Aktionen werden beim Mandanten des Netzbetreibers ausgeführt.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Stellen Sie sicher, dass Sie über die erforderlichen Rechte im Anbieter Mandanten verfügen

Wenn Sie sich beim Microsoft 365 Admin Center als globaler Administrator angemeldet haben, können Sie nur neue Domänen hinzufügen. 

Um die Rolle zu überprüfen, die Sie haben, melden Sie sich bitte beim Microsofthttps://portal.office.com)365 Admin Center an (wechseln Sie zu > **aktive**Benutzer **von Benutzern,** und überprüfen Sie, ob Sie über eine globale Administrator Rolle verfügen. 

Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Office 365 finden Sie unter Informationen zu [Office 365-Administratorrollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Dem Mandanten eine Basisdomäne hinzufügen und diese überprüfen

1. Wechseln Sie im Microsoft 365 Admin Center zu **Setup** > **Domains** > **Domain hinzufügen**.
2. Geben Sie im Feld Ihre **eigene Domäne eingeben** den FQDN der Basisdomäne ein. Im folgenden Beispiel ist die Basisdomäne *Customers.adatum.biz*.

    ![Screenshot mit der Seite "Domäne hinzufügen"](media/direct-routing-2-sbc-add-domain.png)

3. Klicken Sie auf **Weiter**.
4. Im Beispiel hat der Mandant bereits adatum.biz als bestätigten Domänennamen. Der Assistent fragt keine zusätzliche Überprüfung ab, da Customers.adatum.biz eine Unterdomäne für den bereits registrierten Namen ist. Wenn Sie jedoch einen FQDN hinzufügen, der noch nicht überprüft wurde, müssen Sie den Verifizierungsprozess durchlaufen. Der Verifizierungsprozess wird im [folgenden beschrieben](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

    ![Screenshot mit Bestätigung eines überprüften Domänennamens](media/direct-routing-3-sbc-verify-domain.png)

5. Klicken Sie auf **weiter**, und wählen Sie auf der Seite **DNS-Einstellungen aktualisieren** die Option **Ich möchte die DNS-Einträge selbst hinzufügen** aus, und klicken Sie auf **weiter**.
6. Deaktivieren Sie auf der nächsten Seite alle Werte (es sei denn, Sie möchten den Domänennamen für Exchange, SharePoint oder Teams/Skype for Business verwenden), klicken Sie auf **weiter**, und klicken Sie dann auf **Fertig stellen**. Stellen Sie sicher, dass sich Ihre neue Domäne im Status "Setup abgeschlossen" befindet.

    ![Screenshot mit Domänen mit dem Status "Setup abgeschlossen"](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>Aktivieren des Domänennamens

Nachdem Sie einen Domänennamen registriert haben, müssen Sie ihn aktivieren, indem Sie mindestens einen von E1, E3 oder E5 lizenzierten Benutzer hinzufügen und dem FQDN-Teil der SIP-Adresse, die der erstellten Basisdomäne entspricht, eine SIP-Adresse zuweisen. 

*Weitere Informationen zum Hinzufügen von Benutzern in Office 365-Organisationen finden Sie [unter Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*

Beispiel: Test@Customers.adatum.biz

![Screenshot der Seite "Basisdomänen Aktivierung"](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrieren eines Unterdomänen namens in einem Kundenmandanten

Sie müssen für jeden Kunden einen eindeutigen Subdomain-Namen erstellen. In diesem Beispiel wird eine Subdomain-sbc1.Customers.adatum.biz in einem Mandanten mit dem standardmäßigen Domänennamen woodgrovebank.US erstellt.

**Alle nachstehenden Aktionen befinden sich im Kundenmandanten.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Sicherstellen, dass Sie über die erforderlichen Rechte im Kundenmandanten verfügen

Wenn Sie sich beim Microsoft 365 Admin Center als globaler Administrator angemeldet haben, können Sie nur neue Domänen hinzufügen. 

Um die Rolle zu überprüfen, die Sie haben, melden Sie sich bitte beim Microsofthttps://portal.office.com)365 Admin Center an (wechseln Sie zu > **aktive**Benutzer **von Benutzern,** und überprüfen Sie, ob Sie über eine globale Administrator Rolle verfügen. 

Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Office 365 finden Sie unter Informationen zu [Office 365-Administratorrollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Hinzufügen einer Unterdomäne zum Kundenmandanten und zur Überprüfung
1. Wechseln Sie im Microsoft 365 Admin Center zu **Setup** > **Domains** > **Domain hinzufügen**.
2. Geben Sie im Feld Ihre **eigene Domäne eingeben** den FQDN der Unterdomäne für diesen Mandanten ein. Im folgenden Beispiel ist die Unterdomäne sbc1.Customers.adatum.biz.

    ![Screenshot der Seite "Domäne hinzufügen"](media/direct-routing-5-sbc-add-customer-domain.png)

3. Klicken Sie auf **Weiter**.
4. Der FQDN wurde nie im Mandanten registriert. Im nächsten Schritt müssen Sie die Domäne überprüfen. Wählen Sie **stattdessen TXT-Eintrag hinzufügen**aus. 

    ![Screenshot der Seite "Domäne überprüfen"](media/direct-routing-6-sbc-verify-customer-domain.png)

5. Klicken Sie auf **weiter**, und notieren Sie sich den generierten txt-Wert, um den Domänennamen zu überprüfen.

    ![Screenshot von Texteinträgen auf der Seite "Domäne überprüfen"](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Erstellen Sie den TXT-Eintrag mit dem Wert aus dem vorherigen Schritt im DNS-Hostinganbieter des Carriers.

    ![Screenshot mit dem Erstellen des txt-Eintrags](media/direct-routing-8-sbc-txt-record.png)

    Weitere Informationen finden Sie unter [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Wechseln Sie zurück zum Microsoft 365 Admin Center des Kunden, und klicken Sie auf **überprüfen**. 
8. Wählen Sie auf der nächsten Seite **die Option Ich füge die DNS-Einträge selbst hinzu** , und klicken Sie auf **weiter**.

    ![Screenshot der Optionen auf der Seite "DNS-Einstellungen aktualisieren"](media/direct-routing-9-sbc-update-dns.png)

9. Deaktivieren Sie auf der Seite **Onlinedienste auswählen** alle Optionen, und klicken Sie auf **weiter**.

    ![Screenshot der Seite "wählen Sie Ihre Onlinedienste aus"](media/direct-routing-10-sbc-choose-services.png)

10. Klicken Sie auf der Seite " **DNS-Einstellungen aktualisieren** " auf **Fertig stellen** .

    ![Screenshot der Seite "DNS-Einstellungen aktualisieren"](media/direct-routing-11-sbc-update-dns-finish.png)

11. Stellen Sie sicher, dass der Status **Setup abgeschlossen**ist. 
    
    ![Screenshot der Seite mit dem Status "Setup abgeschlossen"](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a>Aktivieren des Unterdomänen namens

Nachdem Sie einen Domänennamen registriert haben, müssen Sie ihn aktivieren, indem Sie mindestens einen Benutzer hinzufügen und eine SIP-Adresse mit dem FQDN-Teil der SIP-Adresse zuweisen, die der erstellten Unterdomäne im Kundenmandanten entspricht.

*Weitere Informationen zum Hinzufügen von Benutzern in Office 365-Organisationen finden Sie [unter Hilfe zu Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*

Beispiel: Test@sbc1.Customers.adatum.biz

![Screenshot der Aktivierung der Subdomain-Seite](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Erstellen eines Trunks und Bereitstellen von Benutzern

Mit der ersten Version des direkten Routings benötigte Microsoft einen trunk, der jedem bedienten Mandanten (Kundenmandant) mithilfe von New-CSOnlinePSTNGateway hinzugefügt werden musste.

Dies hat sich jedoch aus zwei Gründen nicht als optimal erwiesen:
 
- **Overhead-Management**. Wenn Sie beispielsweise einen SBC entladen oder entladen, werden einige Parameter wie das Aktivieren oder Deaktivieren der medienumgehung geändert. Das Ändern des Ports erfordert das Ändern von Parametern in mehreren Mandanten (durch Ausführen von "Satz-CSOnlinePSTNGateway)", ist aber tatsächlich derselbe SBC. 

-  **Overhead-Bearbeitung**. Sammeln und Überwachen von trunk-Integritätsdaten – die SIP-Optionen, die aus mehreren logischen Stämmen gesammelt wurden, die in Wirklichkeit derselbe SBC und derselbe physische Stamm sind, verlangsamen die Verarbeitung der Routingdaten.
 
Basierend auf diesem Feedback führt Microsoft eine neue Logik ein, um die Stämme für die Kundenmandanten bereitzustellen.

Es wurden zwei neue Entitäten eingeführt:
-    Ein Träger trunk, der im Carrier-Mandanten mit dem Befehl New-CSOnlinePSTNGateway registriert ist, beispielsweise New-CSOnlinePSTNGateway-FQDN Customers.adatum.biz-SIPSignalingport 5068-ForwardPAI $true.

-    Ein abgeleiteter Stamm, für den keine Registrierung erforderlich ist. Es ist einfach ein gewünschter Hostname, der aus dem Carrier trunk hinzugefügt wurde. Er leitet alle Konfigurationsparameter vom Netzbetreiber Stamm ab. Der abgeleitete Stamm muss nicht in PowerShell erstellt werden, und die Zuordnung zum Netzbetreiber trunk basiert auf dem FQDN-Namen (siehe Details unten).

**Bereitstellungslogik und-Beispiel**

-    Carrier müssen nur einen einzigen trunk (Carrier trunk in der Carrier-Domäne) einrichten und verwalten, indem Sie den Befehl "CSOnlinePSTNGateway" verwenden. Im obigen Beispiel ist adatum.biz;
-    Im Kundenmandanten muss der Netzbetreiber nur den FQDN des abgeleiteten Trunks zu den VoIP-Routing Richtlinien der Benutzer hinzufügen. Die Ausführung von New-CSOnlinePSTNGateway für einen trunk ist nicht erforderlich.
-    Der abgeleitete Stamm, wie der Name andeutet, erbt oder leitet alle Konfigurationsparameter vom Netzbetreiber Stamm ab. Beispiele
-    Customers.adatum.biz – der Carrier trunk, der im Carrier-Mandanten erstellt werden muss.
-    Sbc1.Customers.adatum.biz – der abgeleitete Stamm in einem Kundenmandanten, der nicht in PowerShell erstellt werden muss.  Sie können einfach den Namen des abgeleiteten Trunks im Mandanten Mandanten in der Online-VoIP-Routing Richtlinie hinzufügen, ohne ihn zu erstellen.
-   Der Netzbetreiber muss den DNS-Eintrag einrichten, der den FQDN des abgeleiteten Trunks zu Carrier SBC-IP-Adresse auflöst.

-    Alle Änderungen, die an einem Netzbetreiber Stamm (auf dem Carrier-Mandanten) vorgenommen wurden, werden automatisch auf abgeleitete Stämme angewendet. Beispielsweise können Netzbetreiber einen SIP-Port auf dem Carrier-trunk ändern, und diese Änderung gilt für alle abgeleiteten Trunks. Neue Logik zum Konfigurieren der Trunks vereinfacht die Verwaltung, da Sie nicht zu jedem Mandanten wechseln und den Parameter für jeden trunk ändern müssen.
-    Die Optionen werden nur an den FQDN des Carrier Trunks gesendet. Der Integritätsstatus des Träger Trunks wird auf alle abgeleiteten Stämme angewendet und für Routingentscheidungen verwendet. Weitere Informationen zu den [Optionen für das direkte Routing](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot).
-    Der Netzbetreiber kann den Kofferraum entladen, und alle abgeleiteten Stämme werden ebenfalls entleert. 
 

**Migration vom Vorgängermodell zum Carrier trunk**
 
Für die Migration von der aktuellen Implementierung des Carrier-Hosted-Modells zum neuen Modell müssen die Netzbetreiber die Stämme für Kundenmandanten neu konfigurieren. Entfernen Sie die Trunks von den Kundenmandanten mithilfe von Remove-CSOnlinePSTNGateway (verlassen des Stamms im Carrier-Mandanten)-

Wir empfehlen, so schnell wie möglich auf die neue Lösung zu migrieren, da wir die Überwachung und Bereitstellung mit dem Carrier und dem abgeleiteten trunk Modell verbessern werden.
 

Lesen Sie dazu die [Anweisungen des SBC-Herstellers](#deploy-and-configure-the-sbc) zum Konfigurieren des Sendens des FQDN-namens von Unterdomänen in der Kontakt Kopfzeile.

## <a name="considerations-for-setting-up-muti-tenant-failover"></a>Überlegungen zum Einrichten eines Muti-Mandanten-Failovers 

Zum Einrichten eines Failovers für eine Multi-Tenant-Umgebung müssen Sie die folgenden Schritte ausführen:

- Fügen Sie für jeden Mandanten die FQDNs für zwei unterschiedliche SBCS hinzu.  Beispiel:

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- Geben Sie in den Online-VoIP-Routing Richtlinien der Benutzer beide SBCS.  Wenn ein SBC fehlschlägt, leitet die Routing Richtlinie Anrufe an den zweiten SBC weiter.


## <a name="see-also"></a>Siehe auch

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)

