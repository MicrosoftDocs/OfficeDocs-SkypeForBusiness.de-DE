---
title: Konfigurieren des Session Border Controllers – mehrere Mandanten
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie einen Session Border Controller (SBC) für die Verwendung mehrerer Mandanten für Microsoft-Partner und/oder PSTN-Netzbetreiber konfigurieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 97995b2da79f7e3ddd781615ccddfc0dd64ae0b6
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457225"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Konfigurieren eines Session Border Controllers für mehrere Mandanten

Direct Routing unterstützt die Konfiguration eines Session Border Controllers (SBC), um mehrere Mandanten zu unterstützen.

> [!NOTE]
> Dieses Szenario ist für Microsoft-Partner und/oder PSTN-Netzbetreiber ausgelegt, die weiter später in diesem Dokument als Netzbetreiber bezeichnet werden. Ein Netzbetreiber verkauft Telefoniedienste, die an Microsoft Teams kunden geliefert werden. 

Ein Netzbetreiber:
- Stellt einen SBC in seinen Rechenzentren und verwaltet diesen (Kunden müssen keinen SBC implementieren und empfangen Telefoniedienste vom Netzbetreiber im Teams-Client).
- Verbindet den SBC mit mehreren Mandanten.
- Stellt Kunden PSTN-Dienste (Public Switched Telephone Network) zur Verfügung.
- Verwaltet die End-to-End-Verwaltung der Anrufqualität.
- Gebühren separat für PSTN-Dienste.

Microsoft verwaltet keine Netzbetreiber. Microsoft bietet Teams Telefon Private Branch-Exchange (PBX) und einen Teams an. Microsoft zertifiziert außerdem Telefone und Certifizieren von SBCs, die mit der Teams Telefonsystem. Stellen Sie vor der Auswahl eines Netzbetreibers sicher, dass Ihre Wahl über einen zertifizierten SBC verfügt und die End-to-End-Sprachqualität verwalten kann.

Im Folgenden werden die technischen Implementierungsschritte zum Konfigurieren des Szenarios beschrieben.

**Nur Netzbetreiber:**
1. Stellen Sie den SBC gemäß den Anweisungen der zertifizierten [SBC-Hersteller für das Hostingszenario zur Verfügung](#deploy-and-configure-the-sbc).
2. Registrieren Sie einen Basisdomänennamen im Carrier-Mandanten, und fordern Sie ein Platzhalterzertifikat an.
3. Registrieren Sie eine Unterdomäne für jeden Kunden, der Teil der Basisdomäne ist.

**Carrier mit einem globalen Kundenadministrator:**
1. Fügen Sie den Namen der Unterdomäne dem Kunden-Mandanten hinzu.
2. Aktivieren Sie den Namen der Unterdomäne.
3. Konfigurieren Sie den Trunk vom Netzbetreiber zum Kunden-Mandanten, und stellen Sie Benutzer zur Verfügung.

*Stellen Sie sicher, dass Sie die DNS-Grundlagen kennen und wissen, wie der Domänenname in Microsoft 365. Lesen [Sie Hilfe zu Microsoft 365 Domänen erhalten,](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) bevor Sie fortfahren.*

## <a name="deploy-and-configure-the-sbc"></a>Bereitstellen und Konfigurieren des SBC

Ausführliche Schritte zum Bereitstellen und Konfigurieren von SBCs für ein SBC-Hostingszenario finden Sie in der Dokumentation des SBC-Anbieters.

- **AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in "Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note". 
- **Oracle:** [Hinweise zur Direct Routing-Konfiguration](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html). Die Konfiguration des SBC-Hostingszenarios wird im Abschnitt "Microsoft" beschrieben. 
- **Menübandkommunikation:**  Im Konfigurationshandbuch für Ribbon [Communications SBC Core Microsoft Teams](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) finden Sie eine Dokumentation zum Konfigurieren von Ribbon Core Series SBCs und auf dieser Seite bewährte Methode des Menübands – Konfigurieren von Netzbetreibern für [Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier).
- **TE-Systems (anynode):**  Bitte registrieren Sie sich [auf der Te-Systems-Community für](https://community.te-systems.de/) Dokumentationen und Beispiele zum Konfigurieren von anynode SBC für mehrere Mandanten.
- **Metaswitch:**  Bitte registrieren Sie sich auf Community [Metaswitch-Seite,](https://manuals.metaswitch.com/MAN39555) um Dokumentation zum Aktivieren von Perimeta SBC für mehrere Mandanten zu erhalten.

> [!NOTE]
> Stellen Sie sicher, dass Sie wissen, wie die Kopfzeile "Kontakt" konfiguriert wird. Die Kontaktkopfzeile wird verwendet, um den Kunden-Mandanten in der eingehenden Einladungsnachricht zu finden. 

## <a name="register-a-base-domain-and-subdomains"></a>Registrieren einer Basisdomäne und Unterdomänen

Für das Hostingszenario müssen Sie:

- Ein Basisdomänenname im Besitz des Netzbetreibers.
- Eine Unterdomäne, die Teil des Basisdomänennamens in jedem Kunden-Mandanten ist.

Im folgenden Beispiel:

- Adatum ist ein Netzbetreiber, der mehrere Kunden durch die Bereitstellung von Internet- und Telefoniediensten bedient.
- Die Woodgrove Bank, Contoso und Adventure Works sind drei Kunden, die über Microsoft 365 Domänen verfügen, aber die Telefoniedienste von Adatum erhalten.

Unterdomänen **MÜSSEN** dem FQDN-Namen des Trunks entsprechen, der für den Kunden konfiguriert wird, und dem FQDN im Kontaktheader beim Senden der Einladung zu Microsoft 365. 

Wenn ein Anruf bei der Microsoft 365 Direct Routing-Schnittstelle eintrifft, verwendet die Schnittstelle den Kontaktheader, um den Mandanten zu finden, in dem der Benutzer gesucht werden soll. Direct Routing verwendet für die Einladung keine Telefonnummern-Suche, da einige Kunden möglicherweise Nicht-DID-Nummern haben, die sich in mehreren Mandanten überschneiden können. Daher ist der FQDN-Name im Kontaktheader erforderlich, um den genauen Mandanten zu identifizieren, um den Benutzer nach der Telefonnummer zu suchen.

*Weitere Informationen zum Erstellen von Domänennamen in Microsoft 365 finden Sie unter [Hilfe zu Microsoft 365 Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef).*

Das folgende Diagramm fasst die Anforderungen für die Basis von Domäne, Unterdomänen und Kontaktheadern zusammen.

![Diagramm mit den Anforderungen an Domänen und Kontaktkopfzeile.](media/direct-routing-1-sbc-requirements.png)

Für die SBC ist ein Zertifikat erforderlich, um die Verbindungen zu authentifizieren. Für das SBC-Hostingszenario muss der Netzbetreiber ein Zertifikat mit CN und/oder SAN *\*.base_domain (\** z. B. customers.adatum.biz) anfordern. Dieses Zertifikat kann verwendet werden, um Verbindungen mit mehreren Mandanten zu authentifizieren, die über einen einzigen SBC bedient werden.

Die folgende Tabelle ist ein Beispiel für eine Konfiguration.


|Neuer Domänenname |Typ|Registriert  |Zertifikat-CN/SAN für SBC  |Tenant default domain in the example  |FQDN-Name, den SBC beim Senden von Anrufen an Benutzer im Kontaktkopf enthalten muss|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Basis     |     Im Netzbetreiber-Mandanten  |    \*.customers.adatum.biz  |   adatum.biz      |NA, dies ist ein Dienst mandant, keine Benutzer. |
|sbc1.customers.adatum.biz|    Subdomain  |    In einem Kunden-Mandanten  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Subdomain | In einem Kunden-Mandanten   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Subdomain | In einem Kunden-Mandanten |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

Führen Sie die folgenden Schritte aus, um die Basis- und Unterdomänen zu konfigurieren. In diesem Beispiel werden ein Basisdomänenname (customers.adatum.biz) und eine Unterdomäne für einen Kunden (sbc1.customers.adatum.biz im Woodgrove Bank-Mandanten) konfiguriert.

> [!NOTE]
> Verwenden sbcX.customers.adatum.biz, um Sprache im Mandanten des Netzbetreibers zu aktivieren; sbcX kann ein beliebiger eindeutiger und gültiger alphanumerischer Hostname sein.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registrieren eines Basisdomänennamens im Carrier-Mandanten

**Diese Aktionen werden im Mandanten des Netzbetreibers ausgeführt.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Sicherstellen, dass Sie über entsprechende Rechte im Mandanten des Netzbetreibers verfügen

Sie können neue Domänen nur hinzufügen, wenn Sie sich beim Microsoft 365 Admin Center als globaler Administrator angemeldet haben. 

Um Ihre Rolle zu überprüfen, melden Sie sich beim Microsoft 365 Admin Center an (https://portal.office.com),  >  wechseln Sie zu **BenutzerAktive** Benutzer, und vergewissern Sie sich dann, dass Sie über eine globale Administratorrolle verfügen. 

Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Microsoft 365 finden Sie unter Informationen [zu Administratorrollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Hinzufügen einer Basisdomäne zum Mandanten und Überprüfen der Domäne

1. Wechseln Sie Microsoft 365 Admin Center Zu **SetupDomainsAdd-Domäne** >  > .

2. Geben Sie **im Feld Geben Sie eine Domäne** ein, die Sie besitzen den FQDN der Basisdomäne ein. Im folgenden Beispiel ist die Basisdomäne *customers.adatum.biz*.

    ![Screenshot der Seite "Domäne hinzufügen"](media/direct-routing-2-sbc-add-domain.png)

3. Klicken Sie auf **Weiter**.

4. In diesem Beispiel verfügt der Mandant adatum.biz als überprüften Domänennamen. Der Assistent fordert keine zusätzliche Überprüfung an, da customers.adatum.biz eine Unterdomäne für den bereits registrierten Namen ist. Wenn Sie jedoch einen FQDN hinzufügen, der noch nicht überprüft wurde, müssen Sie den Überprüfungsprozess durchgehen. Der Überprüfungsprozess wird [nachfolgend beschrieben](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

    ![Screenshot, der die Bestätigung eines bestätigten Domänennamens zeigt.](media/direct-routing-3-sbc-verify-domain.png)

5. Klicken **Sie auf** Weiter, und wählen Sie auf der Seite **DNS Einstellungen** aktualisieren die Option Ich füge die **DNS-Einträge** selbst hinzu aus, und klicken Sie auf **Weiter**.

6. Löschen Sie auf der nächsten Seite alle Werte (es sei denn, Sie möchten den Domänennamen für Exchange, SharePoint, Teams oder Skype for Business verwenden), klicken Sie auf **Weiter und dann** auf **Fertig** stellen. Stellen Sie sicher, dass ihre neue Domäne den Status Setup abgeschlossen hat.

    ![Screenshot mit Domänen mit dem Status "Setup abgeschlossen"](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>Aktivieren des Domänennamens

Nachdem Sie einen Domänennamen registriert haben, müssen Sie ihn aktivieren, indem Sie mindestens einen Benutzer mit Telefonsystem-Lizenz hinzufügen und eine SIP-Adresse mit dem FQDN-Teil der SIP-Adresse zuweisen, der der erstellten Basisdomäne zusaiert ist.

> [!NOTE]
> Der Carrier-Mandant muss mindestens eine dem Mandanten zugewiesene Telefonsystem behalten, um das Entfernen des Mandanten Skype for Business vermeiden. 

*Weitere Informationen zum Hinzufügen von Benutzern in Microsoft 365 finden Sie unter Hilfe [zu Microsoft 365 Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef).*

Beispiel: test@customers.adatum.biz

![Screenshot der Aktivierungsseite der Basisdomäne.](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrieren eines Unterdomänennamens in einem Kunden-Mandanten

Sie müssen für jeden Kunden einen eindeutigen Unterdomänennamen erstellen. In diesem Beispiel erstellen wir eine Unterdomäne in sbc1.customers.adatum.biz mit dem Standarddomänennamen woodgrovebank.us.

**Alle nachstehenden Aktionen befinden sich im Kunden-Mandanten.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Sicherstellen, dass Sie über geeignete Rechte im Kunden-Mandanten verfügen

Sie können neue Domänen nur hinzufügen, wenn Sie sich bei der Microsoft 365 Admin Center als globaler Administrator angemeldet haben. 

Um Ihre Rolle zu überprüfen, melden Sie sich beim Microsoft 365 Admin Center an (https://portal.office.com), wechseln Sie zu **BenutzerAktive** >  Benutzer, und vergewissern Sie sich dann, dass Sie über eine globale Administratorrolle verfügen. 

Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Microsoft 365 finden Sie unter Informationen [zu Administratorrollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Hinzufügen einer Unterdomäne zum Kunden-Mandanten und Überprüfen der Unterdomäne
1. Wechseln Sie Microsoft 365 Admin Center Domäne **SetupDomainsAdd** >  > .

2. Geben Sie **im Feld Geben Sie eine** Domäne ein, die Sie besitzen den FQDN der Unterdomäne für diesen Mandanten ein. Im folgenden Beispiel ist die Unterdomäne sbc1.customers.adatum.biz.

    ![Screenshot der Seite "Domäne hinzufügen"](media/direct-routing-5-sbc-add-customer-domain.png)

3. Klicken Sie auf **Weiter**.

4. Der FQDN wurde noch nie im Mandanten registriert. Im nächsten Schritt müssen Sie die Domäne überprüfen. Wählen **Sie Stattdessen TXT-Eintrag hinzufügen aus**. 

    ![Screenshot der Seite "Domäne überprüfen"](media/direct-routing-6-sbc-verify-customer-domain.png)

5. Klicken **Sie auf** Weiter, und notieren Sie sich den zum Überprüfen des Domänennamens generierten TXT-Wert.

    ![Screenshot von Texteinträgen auf der Seite "Domäne überprüfen"](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Erstellen Sie den TXT-Eintrag mit dem Wert aus dem vorherigen Schritt beim DNS-Hostinganbieter des Netzbetreibers.

    ![Screenshot, der zeigt, wie der TXT-Eintrag erstellt wird.](media/direct-routing-8-sbc-txt-record.png)

    Weitere Informationen finden Sie unter [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Wechseln Sie zum Konto des Kunden Microsoft 365 Admin Center und klicken Sie **auf Überprüfen**. 

8. Wählen Sie auf der nächsten Seite **Ich füge die DNS-Einträge selbst hinzu aus** , und klicken Sie auf **Weiter**.

    ![Screenshot der Optionen auf der Seite "DNS-Einstellungen aktualisieren"](media/direct-routing-9-sbc-update-dns.png)

9. Löschen Sie auf **der Seite Onlinedienste auswählen** alle Optionen, und klicken Sie auf **Weiter**.

    ![Screenshot der Seite "Onlinedienste auswählen"](media/direct-routing-10-sbc-choose-services.png)

10. Klicken **Sie auf** der Seite **DNS-Einstellungen aktualisieren auf** Fertig stellen.

    ![Screenshot der Seite "DNS-Einstellungen aktualisieren"](media/direct-routing-11-sbc-update-dns-finish.png)

11. Stellen Sie sicher, dass der Status **Setup abgeschlossen ist**. 
    
    ![Screenshot der Seite mit dem Status "Setup abgeschlossen"](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> Die Basis-URL und die Unterdomäne für den einzelnen Client müssen sich im gleichen Mandanten enthalten, damit Sie einen direkten _Routen-Trunk hinzufügen_ können.

### <a name="activate-the-subdomain-name"></a>Aktivieren des Unterdomänennamens

Nachdem Sie einen Domänennamen registriert haben, müssen Sie ihn aktivieren, indem Sie mindestens einen Benutzer hinzufügen und eine SIP-Adresse mit dem FQDN-Teil der SIP-Adresse zuweisen, die der erstellten Unterdomäne im Kunden-Mandanten zusagt. 

*Weitere Informationen zum Hinzufügen von Benutzern in Microsoft 365 finden Sie unter [Hilfe zu Microsoft 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef).*

Beispiel: test@sbc1.customers.adatum.biz

![Screenshot der Seite "Aktivierung der Unterdomäne"](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Erstellen eines Trunks und Bereitstellen von Benutzern

Bei der ersten Veröffentlichung von Direct-Routing war es erforderlich, dass jedem bedienten Mandanten (Kundenmandant) mithilfe des cmdlets "New-CSOnlinePSTNGateway" ein Trunk hinzugefügt wurde.

Allerdings hat sich diese Methode aus zwei Gründen nicht als optimal erwiesen:
 
- **Mehraufwandsverwaltung**. Das Aus- oder Entladen eines SBC ändert z. B. einige Parameter, z. B. das Aktivieren oder Deaktivieren der Medienumgehung. Das Ändern des Ports erfordert das Ändern von Parametern in mehreren Mandanten (durch Ausführen von Set-CSOnlinePSTNGateway), aber es ist tatsächlich derselbe SBC. 

-  **Mehraufwand für die Verarbeitung** Erfassen und Überwachen von Trunkinte health-Daten – SIP-Optionen, die aus mehreren logischen Trunks gesammelt werden, die in Wirklichkeit der gleiche SBC und der gleiche physische Trunk sind, verlangsamen die Verarbeitung der Routingdaten.
 
Auf der Grundlage dieses Feedbacks bringt Microsoft eine neue Logik zur Bereitstellung der Trunks für die Kunden mandanten ein.

Es wurden zwei neue Entitäten eingeführt:

- Ein carrier trunk registered in the carrier tenant by using the command New-CSOnlinePSTNGateway. Zum Beispiel:  
   
   ```PowerShell
   New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true
    ```

-  Ein abgeleiteter Trunk, für den keine Registrierung erforderlich ist. Dies ist einfach ein gewünschter Hostname, der aus dem Netzbetreiberstamm hinzugefügt wird. Sie leitet alle Konfigurationsparameter vom Carrier Trunk ab. Der abgeleitete Trunk muss nicht in PowerShell erstellt werden, und die Zuordnung mit dem Carrier Trunk basiert auf dem FQDN-Namen (siehe unten).

**Bereitstellungslogik und Beispiel**

- Netzbetreiber müssen nur einen einzigen Trunk (den Carrier Trunk in der Domäne des Netzbetreibers) mithilfe des Befehls "Set-CSOnlinePSTNGateway verwalten. Im vorstehenden Beispiel ist dies adatum.biz.

- Im Kunden-Mandanten muss der Netzbetreiber den abgeleiteten Trunk-FQDN den Sprachroutingrichtlinien der Benutzer hinzufügen. Sie müssen die New-CSOnlinePSTNGateway für einen Trunk nicht ausführen.

- Der abgeleitete Trunk erbt oder leitet, wie der Name vermuten lässt, alle Konfigurationsparameter vom Carrier Trunk ab. 

Beispiele:
- Customers.adatum.biz : der Carrier Trunk, der im Mandanten des Netzbetreibers erstellt werden muss.

- Sbc1.customers.adatum.biz: der abgeleitete Trunk in einem Kunden-Mandanten, der nicht in PowerShell erstellt werden muss.  Sie können einfach den Namen des abgeleiteten Trunks im Kundenmandant in der Online-Voiceroutingrichtlinie hinzufügen, ohne ihn zu erstellen (verwenden Sie den abgeleiteten Trunk-FQDN beim Einrichten der Voice Routing-Richtlinie in TAC unter Teams-Voice-Direct Routing-Voice Routingfeld SBCs registriert).

- Der Netzbetreiber muss einen DNS-Eintrag einrichten, mit dem der abgeleitete Trunk-FQDN mit der IP-Adresse des Netzbetreibers SBC aufgelöst wird.

- Alle Änderungen, die an einem Carrier Trunk (beim Mandanten des Netzbetreibers) vorgenommen werden, werden automatisch auf abgeleitete Trunks angewendet. Beispielsweise können Netzbetreiber einen SIP-Port auf dem Carrier Trunk ändern, und diese Änderung gilt für alle abgeleiteten Trunks. Neue Logik zum Konfigurieren der Trunks vereinfacht die Verwaltung, da Sie nicht zu jedem Mandanten wechseln und den Parameter auf jedem Trunk ändern müssen.

- Die Optionen werden nur an den FQDN des Netzbetreiberstamms gesendet. Der Integritätsstatus des Netzbetreiberstamms wird auf alle abgeleiteten Trunks angewendet und für Routingentscheidungen verwendet. Erfahren Sie mehr über [die Optionen für Direct-Routing](./direct-routing-monitor-and-troubleshoot.md).

- Der Netzbetreiber kann den Trunk des Netzbetreibers entleeren, und alle abgeleiteten Trunks werden ebenfalls entleert. 
 
> [!NOTE]
> Auf den Netzbetreiberstamm angewendete Regeln für die Nummernübersetzung gelten nicht für abgeleitete Trunks. Dies ist ein bekanntes Problem. Als Alternative müssen Für die Mandanten jedes Kunden Regeln für die Nummernübersetzung erstellt werden.

**Migration vom vorherigen Modell zum Carrier Trunk**
 
Für die Migration von der aktuellen Implementierung des gehosteten Modells des Netzbetreibers auf das neue Modell müssen die Netzbetreiber die Trunks für Kunden-Mandanten neu konfigurieren. Entfernen Sie die Trunks von den Kunden mandanten mithilfe Remove-CSOnlinePSTNGateway (der Trunk wird im Mandanten des Netzbetreibers verlassen)-

Wir empfehlen dringend, so bald wie möglich zur neuen Lösung zu migrieren, da wir die Überwachung und Bereitstellung mit dem Netzbetreiber und abgeleiteten Trunkmodell verbessern werden.
 
Weitere Informationen zum Konfigurieren des FQDN-Namens von Unterdomänen im Kontaktheader finden Sie in den [Anweisungen des Anbieters von SBC](#deploy-and-configure-the-sbc).

## <a name="considerations-for-setting-up-multi-tenant-failover"></a>Überlegungen zum Einrichten von Failover mit mehreren Mandanten 

Zum Einrichten des Failovers für eine Umgebung mit mehreren Mandanten müssen Sie die folgenden Schritte ausführen:

- Fügen Sie für jeden Mandanten die FQDNs für zwei verschiedene SBCs hinzu. Zum Beispiel: 

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- Geben Sie in den Online Voice Routing-Richtlinien der Benutzer beide SBCs an. Wenn ein SBC fehlschlägt, werden Von der Routingrichtlinie Aufrufe an den zweiten SBC geroutet.


## <a name="see-also"></a>Mehr dazu

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)
