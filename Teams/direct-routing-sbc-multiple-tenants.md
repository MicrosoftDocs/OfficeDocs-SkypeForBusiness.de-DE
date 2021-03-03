---
title: Konfigurieren des Session Border Controllers – Mehrere Mandanten
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
description: Hier erfahren Sie, wie Sie einen Session Border Controller (SBC) konfigurieren, um mehrere Mandanten für Partner und/oder Netzbetreiber von Microsoft zu verwenden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b81709b46774762036ba9465444d066a0adf019c
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110238"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Konfigurieren eines Session Border Controllers für mehrere Mandanten

Direct Routing unterstützt die Konfiguration eines Session Border Controllers (SBC), um mehrere Mandanten zu unterstützen.

> [!NOTE]
> Dieses Szenario ist für Microsoft-Partner und/oder Netzbetreiber gedacht, die später in diesem Dokument als Netzbetreiber bezeichnet werden. Ein Netzbetreiber verkauft Telefoniedienste, die an Microsoft Teams geliefert werden, an ihre Kunden. 

Ein Netzbetreiber:
- Stellt einen SBC in ihrem Rechenzentrum zur Verfügung und verwaltet diesen (Kunden müssen keinen SBC implementieren und empfangen Telefoniedienste vom Netzbetreiber im Teams-Client).
- Verbindet den SBC mit mehreren Mandanten.
- Stellt Kunden PSTN-Dienste zur Verfügung.
- Verwaltet die End-to-End-Verwaltung der Anrufqualität.
- Gebühren für PSTN-Dienste separat.

Microsoft verwaltet keine Netzbetreiber. Microsoft bietet eine PbX (Microsoft Phone System) und einen Teams-Client. Microsoft zertifiziert außerdem Telefone und certifiziert SBCs, die mit dem Microsoft Phone System verwendet werden können. Bevor Sie einen Netzbetreiber auswählen, stellen Sie sicher, dass Ihre Wahl über einen zertifizierten SBC verfügt und das Ende der Sprachqualität verwalten kann.

Im Folgenden werden die technischen Implementierungsschritte zum Konfigurieren des Szenarios beschrieben.

**Nur Carrier:**
1. Stellen Sie den SBC zur Verfügung, und konfigurieren Sie ihn entsprechend den Anweisungen der zertifizierten [SBC-Anbieter für das Hostingszenario.](#deploy-and-configure-the-sbc)
2. Registrieren Sie einen Basisdomänennamen im Carrier-Mandanten, und fordern Sie ein Platzhalterzertifikat an.
3. Registrieren Sie eine Unterdomäne für jeden Kunden, der Teil der Basisdomäne ist.

**Carrier mit einem globalen Kundenadministrator:**
1. Fügen Sie den Namen der Unterdomäne dem Kunden mandanten hinzu.
2. Aktivieren sie den Namen der Unterdomäne.
3. Konfigurieren Sie den Trunk vom Netzbetreiber zum Kunden-Mandanten, und stellen Sie Benutzer zur Verfügung.

*Bitte stellen Sie sicher, dass Sie mit den Grundlagen von DNS und der Art und Weise, wie der Domänenname in Microsoft 365 oder Office 365 verwaltet wird, wissen. Lesen [Sie "Hilfe zu Microsoft 365- oder Office 365-Domänen erhalten",](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) bevor Sie fortfahren.*

## <a name="deploy-and-configure-the-sbc"></a>Bereitstellen und Konfigurieren des SBC

Ausführliche Schritte zum Bereitstellen und Konfigurieren von SBCs für ein SBC-Hostingszenario finden Sie in der Dokumentation des SBC-Anbieters.

- **AudioCodes: Direct** [Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in "Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note". 
- **Oracle: Hinweise** [zur Direct-Routing-Konfiguration.](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)Die Konfiguration des SBC-Hostingszenarios wird im Abschnitt "Microsoft" beschrieben. 
- **Menübandkommunikation:**  Eine Dokumentation zum Konfigurieren von Ribbon Core Series SBCs und zu dieser Seite "Bewährte Methode für das Menüband – Konfigurieren von Netzbetreibern für [Microsoft Teams Direct Routing SBC Edge"](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier) finden Sie im Konfigurationshandbuch für Ribbon Communications SBC Core Microsoft [Teams.](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)
- **TE-Systems (anynode):**  Registrieren Sie sich auf der [TE-Systems-Communityseite,](https://community.te-systems.de/) um Dokumentationen und Beispiele zum Konfigurieren von anynode SBC für mehrere Mandanten zu erhalten.
- **Metaswitch:**  Registrieren Sie sich auf der [Metaswitch Community-Seite,](https://manuals.metaswitch.com/MAN39555) um Dokumentation zum Aktivieren von Perimeta SBC für mehrere Mandanten zu erhalten.

> [!NOTE]
> Bitte achten Sie darauf, wie die Kopfzeile "Kontakt" konfiguriert wird. Der Kontaktkopf wird verwendet, um den Kunden mandanten in der eingehenden Einladungsnachricht zu finden. 

## <a name="register-a-base-domain-and-subdomains"></a>Registrieren einer Basisdomäne und Unterdomänen

Für das Hostingszenario müssen Sie:
- Ein Basisdomänenname im Besitz des Netzbetreibers.
- Eine Unterdomäne, die Teil des Basisdomänennamens in jedem Kunden mandant ist.

Im folgenden Beispiel:
- Adatum ist ein Netzbetreiber, der mehrere Kunden durch die Bereitstellung von Internet- und Telefoniediensten bedient.
- Die Woodgrove Bank, Contoso und Adventure Works sind drei Kunden, die über Microsoft 365- oder Office 365-Domänen verfügen, aber die Telefoniedienste von Adatum erhalten.

Unterdomänen MÜSSEN dem Namen des FQDN des **Trunks** entsprechen, der für den Kunden konfiguriert wird, und dem FQDN im Kontaktheader, wenn die Einladung an Microsoft 365 oder Office 365 gesendet wird. 

Wenn ein Anruf bei der Microsoft 365- oder Office 365-Direct-Routing-Schnittstelle eintrifft, verwendet die Schnittstelle den Kontaktheader, um den Mandanten zu finden, in dem der Benutzer gesucht werden soll. Direct Routing verwendet für die Einladung keine Telefonnummern-Suche, da einige Kunden möglicherweise Nicht-DID-Nummern haben, die sich in mehreren Mandanten überschneiden können. Daher ist der FQDN-Name im Kontaktkopf erforderlich, um den genauen Mandanten zu identifizieren, nach dem der Benutzer nach der Telefonnummer suchen soll.

*Weitere Informationen zum Erstellen von Domänennamen in Microsoft  [365-](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) oder Office 365-Organisationen finden Sie unter "Hilfe zu Office 365-Domänen".*

Das folgende Diagramm enthält eine Zusammenfassung der Anforderungen an die Basisdomäne, Unterdomänen und den Kontaktheader.

![Diagramm mit Anforderungen an Domänen und Kontaktkopfzeile](media/direct-routing-1-sbc-requirements.png)

Der SBC benötigt ein Zertifikat, um die Verbindungen zu authentifizieren. Für das #A0 muss der Netzbetreiber ein Zertifikat mit CN und/oder SAN .base_domain (z. B. *\* \* ".customers.adatum.biz") anfordern.* Dieses Zertifikat kann verwendet werden, um Verbindungen mit mehreren Mandanten zu authentifizieren, die von einem einzigen SBC bedient werden.


Die folgende Tabelle ist ein Beispiel für eine Konfiguration.


|Neuer Domänenname |Typ|Registriert  |Zertifikat-CN/SAN für SBC  |Tenant default domain in the example  |FQDN-Name, den SBC beim Senden von Anrufen an Benutzer im Kontaktkopf präsentieren muss|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Basis     |     Im Mandanten des Netzbetreibers  |    \*.customers.adatum.biz  |   adatum.biz      |NA, dies ist ein Dienst mandant, keine Benutzer |
|sbc1.customers.adatum.biz|    Subdomain  |    In einem Kunden-Mandanten  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Subdomain | In einem Kunden-Mandanten   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Subdomain | In einem Kunden-Mandanten |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

Führen Sie die nachstehend beschriebenen Schritte aus, um die Basis- und Unterdomänen zu konfigurieren. Im Beispiel konfigurieren wir einen Basisdomänennamen (customers.adatum.biz) und eine Unterdomäne für einen Kunden (sbc1.customers.adatum.biz im Woodgrove Bank-Mandanten).

> [!NOTE]
> Verwenden sbcX.customers.adatum.biz, um Sprache im Mandanten des Netzbetreibers zu aktivieren. sbcX kann ein beliebiger eindeutiger und gültiger alphanumerischer Hostname sein.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registrieren eines Basisdomänennamens im Carrier Tenant

**Diese Aktionen werden im Mandanten des Netzbetreibers ausgeführt.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Sicherstellen, dass Sie über die entsprechenden Rechte im Mandanten des Netzbetreibers verfügen

Sie können neue Domänen nur hinzufügen, wenn Sie sich beim Microsoft 365 Admin Center als globaler Administrator angemeldet haben. 

Um ihre Rolle zu überprüfen, melden Sie sich bitte beim Microsoft 365 Admin Center an ( wechseln Sie zu "Aktive Benutzer", und vergewissern Sie sich dann, dass Sie über eine Rolle als globaler https://portal.office.com)   >  Administrator verfügen. 

Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Microsoft 365 oder Office 365 finden Sie unter ["Informationen zu Administratorrollen".](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Hinzufügen einer Basisdomäne zum Mandanten und Überprüfen dieser Domäne

1. Wechseln Sie im Microsoft 365 Admin Center zu **"Domänen**  >    >  **hinzufügen".**
2. Geben Sie **in das Feld "Domäne eingeben,** die Sie besitzen" den FQDN der Basisdomäne ein. Im folgenden Beispiel ist die Basisdomäne *customers.adatum.biz.*

    ![Screenshot der Seite "Domäne hinzufügen"](media/direct-routing-2-sbc-add-domain.png)

3. Klicken Sie auf **Weiter**.
4. Im Beispiel verfügt der Mandant bereits über adatum.biz als überprüften Domänennamen. Der Assistent fordert keine zusätzliche Überprüfung an, da customers.adatum.biz eine Unterdomäne für den bereits registrierten Namen ist. Wenn Sie jedoch einen FQDN hinzufügen, der zuvor noch nicht überprüft wurde, müssen Sie den Überprüfungsvorgang durchgehen. Der Überprüfungsprozess wird [unten beschrieben.](#add-a-subdomain-to-the-customer-tenant-and-verify-it)

    ![Screenshot mit der Bestätigung eines bestätigten Domänennamens](media/direct-routing-3-sbc-verify-domain.png)

5. Klicken Sie **auf**"Weiter", und wählen Sie auf der Seite **"DNS-Einstellungen** aktualisieren" die Option "Ich füge die **DNS-Einträge selbst hinzu"** aus, und klicken Sie auf **"Weiter".**
6. Löschen Sie auf der nächsten Seite alle Werte (es sei denn, Sie möchten den Domänennamen für Exchange, SharePoint oder Teams/Skype for Business verwenden), klicken Sie auf "Weiter" **und** dann auf "Fertig **stellen".** Stellen Sie sicher, dass die neue Domäne den Status "Setup abgeschlossen" hat.

    ![Screenshot mit Domänen mit dem Status "Setup abgeschlossen"](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>Aktivieren des Domänennamens

Nachdem Sie einen Domänennamen registriert haben, müssen Sie ihn aktivieren, indem Sie mindestens einen Benutzer mit einer Telefonsystemlizenz hinzufügen und ihm eine SIP-Adresse mit dem FQDN-Teil der ERSTELLTen Basisdomäne zuweisen. Die Lizenz kann nach der Domänenaktivierung widerrufen werden (dies kann bis zu 24 Stunden dauern).

> [!NOTE]
> Der Mandanten des Netzbetreibers muss mindestens eine dem Mandanten zugewiesene Telefonsystemlizenz behalten, um das Entfernen der Skype for Business-Konfiguration zu vermeiden. 

*Weitere Informationen zum Hinzufügen von Benutzern in [Microsoft 365-](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) oder Office 365-Organisationen finden Sie unter "Hilfe zu Microsoft 365- oder Office 365-Domänen".*

Beispiel: test@customers.adatum.biz

![Screenshot der Aktivierungsseite der Basisdomäne](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrieren eines Unterdomänennamens in einem Kunden mandant

Sie müssen für jeden Kunden einen eindeutigen Unterdomänennamen erstellen. In diesem Beispiel erstellen wir eine Unterdomäne sbc1.customers.adatum.biz in einem Mandanten mit dem Standarddomänennamen woodgrovebank.us.

**Alle nachstehenden Aktionen befinden sich im Kunden-Mandanten.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Sicherstellen, dass Sie über die entsprechenden Rechte im Kunden mandanten verfügen

Sie können neue Domänen nur hinzufügen, wenn Sie sich beim Microsoft 365 Admin Center als globaler Administrator angemeldet haben. 

Um ihre Rolle zu überprüfen, melden Sie sich bitte beim Microsoft 365 Admin Center an ( wechseln Sie zu "Aktive Benutzer", und vergewissern Sie sich dann, dass Sie über eine Rolle als globaler https://portal.office.com)   >  Administrator verfügen. 

Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Microsoft 365 oder Office 365 finden Sie unter ["Informationen zu Administratorrollen".](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Hinzufügen einer Unterdomäne zum Kunden mandanten und Überprüfen der Unterdomäne
1. Wechseln Sie im Microsoft 365 Admin Center zu **"Domänen**  >    >  **hinzufügen".**
2. Geben Sie **im Feld "Domäne eingeben,** die Sie besitzen" den FQDN der Unterdomäne für diesen Mandanten ein. Im folgenden Beispiel ist die Unterdomäne sbc1.customers.adatum.biz.

    ![Screenshot der Seite "Domäne hinzufügen"](media/direct-routing-5-sbc-add-customer-domain.png)

3. Klicken Sie auf **Weiter**.
4. Der FQDN wurde noch nie im Mandanten registriert. Im nächsten Schritt müssen Sie die Domäne überprüfen. Wählen Sie **stattdessen "Add a TXT record" aus.** 

    ![Screenshot der Seite "Domäne überprüfen"](media/direct-routing-6-sbc-verify-customer-domain.png)

5. Klicken Sie **auf "Weiter",** und notieren Sie sich den zum Überprüfen des Domänennamens generierten TXT-Wert.

    ![Screenshot von Texteinträgen auf der Seite "Domäne überprüfen"](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Erstellen Sie den TXT-Eintrag mit dem Wert aus dem vorherigen Schritt des DNS-Hostinganbieters des Netzbetreibers.

    ![Screenshot, der zeigt, wie der "TXT"-Eintrag erstellt wird](media/direct-routing-8-sbc-txt-record.png)

    Weitere Informationen finden Sie unter "Erstellen von [DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter".](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)

7. Wechseln Sie zurück zum Microsoft 365 Admin Center des Kunden, und klicken Sie auf **"Überprüfen".** 
8. Wählen Sie auf der nächsten Seite **"Ich füge die** DNS-Einträge selbst hinzu" aus, und klicken Sie auf **"Weiter".**

    ![Screenshot der Optionen auf der Seite "DNS-Einstellungen aktualisieren"](media/direct-routing-9-sbc-update-dns.png)

9. Löschen Sie **auf der Seite "Onlinedienste auswählen"** alle Optionen, und klicken Sie auf **"Weiter".**

    ![Screenshot der Seite "Wählen Sie Ihre Onlinedienste aus"](media/direct-routing-10-sbc-choose-services.png)

10. Klicken Sie **auf der** Seite **"DNS-Einstellungen aktualisieren" auf "Fertig** stellen".

    ![Screenshot der Seite "DNS-Einstellungen aktualisieren"](media/direct-routing-11-sbc-update-dns-finish.png)

11. Stellen Sie sicher, dass der Status **"Setup abgeschlossen" ist.** 
    
    ![Screenshot der Seite mit dem Status "Setup abgeschlossen"](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> Die Basis-URL und die Unterdomäne für den einzelnen Client müssen sich auf demselben Mandanten finden, damit Sie einen direkten _Routenstamm hinzufügen_ können.

### <a name="activate-the-subdomain-name"></a>Aktivieren des Unterdomänennamens

Nachdem Sie einen Domänennamen registriert haben, müssen Sie ihn aktivieren, indem Sie mindestens einen Benutzer hinzufügen und eine SIP-Adresse mit dem FQDN-Teil der SIP-Adresse zuweisen, der der erstellten Unterdomäne im Kunden mandanten zusagt. Die Lizenz kann nach der Aktivierung der Unterdomäne vom Benutzer widerrufen werden (dies kann bis zu 24 Stunden dauern).

*Weitere Informationen zum Hinzufügen von Benutzern in [Microsoft 365-](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) oder Office 365-Organisationen finden Sie unter "Hilfe zu Microsoft 365- oder Office 365-Domänen".*

Beispiel: test@sbc1.customers.adatum.biz

![Screenshot der Aktivierung der Unterdomänenseite](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Erstellen eines Trunks und Bereitstellen von Benutzern

Bei der ersten Veröffentlichung von Direct Routing benötigte Microsoft einen Trunk, der jedem bedienten Mandanten (Kundenmandant) mithilfe von New-CSOnlinePSTNGateway hinzugefügt werden musste.

Dies hat sich jedoch aus zwei Gründen nicht als optimal erwiesen:
 
- **Verwaltung des Aufwands.** Das Aus- oder Entleeren eines SBC ändert z. B. einige Parameter, z. B. das Aktivieren oder Deaktivieren der Medienumgehung. Das Ändern des Ports erfordert das Ändern von Parametern in mehreren Mandanten (durch Ausführen von Set-CSOnlinePSTNGateway), ist aber tatsächlich der gleiche SBC. 

-  **Verarbeitung des Aufwands.** Erfassen und Überwachen von Trunkzustandsdaten – SIP-Optionen, die aus mehreren logischen Trunks gesammelt werden, die tatsächlich denselben SBC und den gleichen physischen Trunk sind, verlangsamen die Verarbeitung der Routingdaten.
 
Auf der Grundlage dieses Feedbacks bringt Microsoft eine neue Logik für die Bereitstellung der Trunks für die Kunden mandanten ein.

Es wurden zwei neue Entitäten eingeführt:
-    Ein Carrier Trunk, der im Carrier Tenant mit dem Befehl "New-CSOnlinePSTNGateway" registriert ist, z. B. New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.

-    Ein abgeleiteter Trunk, für den keine Registrierung erforderlich ist. Es ist einfach ein gewünschter Hostname, der aus dem Carrier Trunk hinzugefügt wird. Er leitet alle Konfigurationsparameter vom Carrier Trunk ab. Der abgeleitete Trunk muss nicht in PowerShell erstellt werden, und die Zuordnung mit dem Carrier Trunk basiert auf dem Namen des FQDNs (siehe details unten).

**Bereitstellungslogik und Beispiel**

-    Netzbetreiber müssen nur einen einzigen Trunk (Carrier Trunk in der Domäne des Netzbetreibers) mithilfe des Befehls "Set-CSOnlinePSTNGateway" einrichten und verwalten. Im vorstehenden Beispiel ist dies adatum.biz;
-    Im Mandanten des Kunden muss der Netzbetreiber den abgeleiteten Trunk-FQDN nur den Sprachroutingrichtlinien der Benutzer hinzufügen. Es ist nicht nötig, New-CSOnlinePSTNGateway für einen Trunk ausführen.
-    Der abgeleitete Trunk erbt oder leitet, wie der Name bereits sagt, alle Konfigurationsparameter vom Carrier Trunk ab. Beispiele:
-    Customers.adatum.biz – der Carrier Trunk, der im Mandanten des Netzbetreibers erstellt werden muss.
-    Sbc1.customers.adatum.biz – der abgeleitete Trunk in einem Kunden-Mandanten, der nicht in PowerShell erstellt werden muss.  Sie können einfach den Namen des abgeleiteten Trunks im Kunden mandanten in der Online-Voiceroutingrichtlinie hinzufügen, ohne sie zu erstellen.
-   Der Netzbetreiber muss einen DNS-Eintrag einrichten, mit dem der abgeleitete Trunk-FQDN zur SBC-IP-Adresse des Netzbetreibers aufgelöst wird.

-    Alle Änderungen, die an einem Carrier Trunk (auf dem Mandanten des Netzbetreibers) vorgenommen werden, werden automatisch auf abgeleitete Trunks angewendet. So können Netzbetreiber beispielsweise einen SIP-Port auf dem Carrier Trunk ändern, und diese Änderung gilt für alle abgeleiteten Trunks. Neue Logik zum Konfigurieren der Trunks vereinfacht die Verwaltung, da Sie nicht zu jedem Mandanten wechseln und den Parameter auf jedem Trunk ändern müssen.
-    Die Optionen werden nur an den Carrier Trunk FQDN gesendet. Der Integritätsstatus des Carrier Trunks wird auf alle abgeleiteten Trunks angewendet und für Routingentscheidungen verwendet. Erfahren Sie mehr über [die Optionen für das direkte Routing.](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)
-    Der Carrier kann den Carrier Trunk entleeren, und alle abgeleiteten Trunks werden ebenfalls entleert. 
 

**Migration vom vorherigen Modell zum Carrier Trunk**
 
Für die Migration von der aktuellen Implementierung des gehosteten Modells des Netzbetreibers zum neuen Modell müssen die Netzbetreiber die Trunks für Kunden mandanten neu konfigurieren. Entfernen Sie die Trunks der Kunden mandanten mithilfe Remove-CSOnlinePSTNGateway (lassen Sie den Trunk im Mandanten des Netzbetreibers) –

Wir empfehlen dringend, so bald wie möglich zur neuen Lösung zu migrieren, da wir die Überwachung und Bereitstellung mit dem Carrier- und abgeleiteten Trunkmodell verbessern werden.
 

Lesen Sie die Anweisungen des [Anbieters SBC](#deploy-and-configure-the-sbc) zum Konfigurieren des FQDN-Namens von Unterdomänen im Kontaktheader.

## <a name="considerations-for-setting-up-muti-tenant-failover"></a>Überlegungen zum Einrichten des Failovers für den muti-Mandanten 

Zum Einrichten des Failovers für eine Umgebung mit mehreren Mandanten müssen Sie die folgenden Schritte ausführen:

- Fügen Sie für jeden Mandanten die FQDNs für zwei unterschiedliche SBCs hinzu.  Beispiel:

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- Geben Sie in den Richtlinien für das Online-Voicerouting der Benutzer beide SBCs an.  Wenn ein SBC fehlschlägt, werden von der Routingrichtlinie Aufrufe an den zweiten SBC weiterleiten.


## <a name="see-also"></a>Siehe auch

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)
