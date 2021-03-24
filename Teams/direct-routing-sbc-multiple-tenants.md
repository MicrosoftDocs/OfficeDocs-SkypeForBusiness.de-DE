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
description: Erfahren Sie, wie Sie einen Session Border Controller (SBC) so konfigurieren, dass mehrere Mandanten für Microsoft-Partner und/oder PSTN-Netzbetreiber bereitgestellt werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 742b02709585e9a25b170bc99aab3d1939d63f10
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096531"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Konfigurieren eines Session Border Controllers für mehrere Mandanten

Direct Routing unterstützt das Konfigurieren eines Session Border Controllers (SBC) für mehrere Mandanten.

> [!NOTE]
> Dieses Szenario ist für Microsoft-Partner und/oder PSTN-Netzbetreiber konzipiert, die später in diesem Dokument als Netzbetreiber bezeichnet werden. Ein Netzbetreiber verkauft Telefoniedienste, die an Microsoft Teams geliefert werden, an ihre Kunden. 

Ein Netzbetreiber:
- Stellt einen SBC in ihrem Rechenzentrum zur Verfügung und verwaltet diesen (Kunden müssen keinen SBC implementieren, und sie erhalten Telefoniedienste vom Netzbetreiber im Teams-Client).
- Verbindet den SBC mit mehreren Mandanten.
- Stellt PstN-Dienste für Kunden zur Verfügung.
- Verwaltet die Anrufqualität von Ende zu Ende.
- Gebühren separat für PSTN-Dienste.

Microsoft verwaltet keine Netzbetreiber. Microsoft bietet eine PBX (Microsoft Phone System) und einen Teams-Client an. Microsoft zertifiziert auch Telefone und zertifiziert SBCs, die mit dem Microsoft Phone System verwendet werden können. Stellen Sie vor der Auswahl eines Netzbetreibers sicher, dass Ihre Wahl über einen zertifizierten SBC verfügt und die Sprachqualität von Ende zu Ende verwalten kann.

Im Folgenden sind die technischen Implementierungsschritte zum Konfigurieren des Szenarios beschrieben.

**Nur Netzbetreiber:**
1. Stellen Sie den SBC zur Verfügung, und konfigurieren Sie ihn gemäß den Anweisungen der zertifizierten [SBC-Anbieter für das Hostingszenario.](#deploy-and-configure-the-sbc)
2. Registrieren Sie einen Basisdomänennamen im Netzbetreiber-Mandanten, und fordern Sie ein Platzhalterzertifikat an.
3. Registrieren Sie eine Unterdomäne für jeden Kunden, der Teil der Basisdomäne ist.

**Netzbetreiber mit einem globalen Kundenadministrator:**
1. Fügen Sie dem Kunden-Mandanten den Namen der Unterdomäne hinzu.
2. Aktivieren Sie den Namen der Unterdomäne.
3. Konfigurieren Sie den Trunk vom Netzbetreiber zum Kunden-Mandanten, und stellen Sie Benutzer zur Verfügung.

*Bitte stellen Sie sicher, dass Sie die GRUNDLAGEN des DNS verstehen und wissen, wie der Domänenname in Microsoft 365 oder Office 365 verwaltet wird. Lesen [Sie Hilfe zu Microsoft 365- oder Office 365-Domänen](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) erhalten, bevor Sie fortfahren.*

## <a name="deploy-and-configure-the-sbc"></a>Bereitstellen und Konfigurieren des SBC

Die detaillierten Schritte zum Bereitstellen und Konfigurieren von SBCs für ein SBC-Hostingszenario finden Sie in der Dokumentation des SBC-Anbieters.

- **AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in "Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note". 
- **Oracle:** [Direct Routing Configuration notes](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html), the configuration of the SBC hosting scenario is described in the "Microsoft" section. 
- **Menübandkommunikation:**  Informationen zum Konfigurieren von Ribbon Core Series SBCs finden Sie im Konfigurationshandbuch für Ribbon [Communications SBC Core Microsoft Teams](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) und auf dieser Seite Bewährte Vorgehensweise im Menüband – Konfigurieren von Netzbetreibern für Microsoft Teams Direct Routing [SBC Edge.](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)
- **TE-Systems (Anynode):**  Registrieren Sie sich auf der [TE-Systems Community-Seite,](https://community.te-systems.de/) um Dokumentationen und Beispiele zum Konfigurieren von anynode SBC für mehrere Mandanten zu erhalten.
- **Metaschalter:**  Registrieren Sie sich auf der [Metaswitch Community-Seite,](https://manuals.metaswitch.com/MAN39555) um eine Dokumentation zum Aktivieren von Perimeta SBC für mehrere Mandanten zu erhalten.

> [!NOTE]
> Achten Sie darauf, wie Sie die Kopfzeile "Kontakt" konfigurieren. Der Kontaktkopf wird verwendet, um den Kunden-Mandanten in der eingehenden Einladungsnachricht zu finden. 

## <a name="register-a-base-domain-and-subdomains"></a>Registrieren einer Basisdomäne und Unterdomänen

Für das Hostingszenario müssen Sie erstellen:
- Ein Basisdomänenname, der sich im Besitz des Netzbetreibers befindet.
- Eine Unterdomäne, die Teil des Basisdomänennamens in jedem Kundend mandanten ist.

Im folgenden Beispiel:
- Adatum ist ein Netzbetreiber, der mehrere Kunden durch Bereitstellung von Internet- und Telefoniediensten bedient.
- Die Woodgrove Bank, Contoso und Adventure Works sind drei Kunden, die über Microsoft 365- oder Office 365-Domänen verfügen, aber die Telefoniedienste von Adatum erhalten.

Unterdomänen MÜSSEN mit dem FQDN-Namen des **Trunks** übereinstimmen, der für den Kunden konfiguriert wird, und dem FQDN im Kontaktkopf, wenn die Einladung an Microsoft 365 oder Office 365 gesendet wird. 

Wenn ein Anruf bei der Microsoft 365- oder Office 365 Direct Routing-Schnittstelle eintrifft, verwendet die Schnittstelle den Kontaktkopf, um den Mandanten zu finden, in dem der Benutzer gesucht werden soll. Bei Direct Routing wird die Telefonnummern-Suche auf der Einladung nicht verwendet, da einige Kunden möglicherweise Nicht-DID-Nummern haben, die sich in mehreren Mandanten überschneiden können. Daher ist der FQDN-Name im Kontaktkopf erforderlich, um den genauen Mandanten zu identifizieren, um den Benutzer nach der Telefonnummer zu suchen.

*Weitere Informationen zum Erstellen von Domänennamen in Microsoft 365- oder Office 365-Organisationen finden Sie unter Hilfe zu [Office 365-Domänen.](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)*

Im folgenden Diagramm sind die Anforderungen an Die Basisdomäne, Unterdomänen und Den Kopfzeile "Kontakt" zusammengefasst.

![Diagramm mit Anforderungen an Domänen und Kontaktkopfzeile](media/direct-routing-1-sbc-requirements.png)

Für den SBC ist ein Zertifikat erforderlich, um die Verbindungen zu authentifizieren. Für das SBC-Hostingszenario muss der Netzbetreiber ein Zertifikat mit CN und/oder SAN .base_domain (z. B. *\* \* .customers.adatum.biz) anfordern.* Dieses Zertifikat kann verwendet werden, um Verbindungen mit mehreren Mandanten zu authentifizieren, die von einem einzelnen SBC aus bedient werden.


Die folgende Tabelle ist ein Beispiel für eine Konfiguration.


|Neuer Domänenname |Typ|Registriert  |Zertifikat-CN/SAN für SBC  |Mandanten-Standarddomäne im Beispiel  |FQDN-Name, den SBC beim Senden von Anrufen an Benutzer im Kontaktkopf präsentieren muss|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Basis     |     Im Netzbetreiber-Mandanten  |    \*.customers.adatum.biz  |   adatum.biz      |NA, dies ist ein Dienst-Mandant, keine Benutzer |
|sbc1.customers.adatum.biz|    Subdomain  |    In einem Kunden mandanten  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Subdomain | In einem Kunden mandanten   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Subdomain | In einem Kunden mandanten |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

Zum Konfigurieren der Basis- und Unterdomänen führen Sie die nachstehend beschriebenen Schritte aus. Im Beispiel konfigurieren wir einen Basisdomänennamen (customers.adatum.biz) und eine Unterdomäne für einen Kunden (sbc1.customers.adatum.biz im Mandanten der Woodgrove Bank).

> [!NOTE]
> Verwenden sbcX.customers.adatum.biz, um die Sprachsteuerung im Netzbetreiber-Mandanten zu aktivieren. sbcX kann ein beliebiger eindeutiger und gültiger alphanumerischer Hostname sein.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registrieren eines Basisdomänennamens im Netzbetreiber-Mandanten

**Diese Aktionen werden im Netzbetreiber-Mandanten ausgeführt.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Sicherstellen, dass Sie über die entsprechenden Rechte im Netzbetreiber-Mandanten verfügen

Sie können neue Domänen nur hinzufügen, wenn Sie sich beim Microsoft 365 Admin Center als globaler Administrator angemeldet haben. 

Um die rolle zu überprüfen, die Sie haben, melden Sie sich bitte beim Microsoft 365 Admin Center an ( , wechseln Sie zu Aktive Benutzer , und überprüfen Sie dann, ob Sie über eine Rolle des globalen https://portal.office.com)   >  Administrators verfügen. 

Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Microsoft 365 oder Office 365 finden Sie unter [Informationen zu Administratorrollen.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Hinzufügen einer Basisdomäne zum Mandanten und Überprüfen der Domäne

1. Wechseln Sie im Microsoft 365 Admin Center zu **Domäne**  >  **"Domänen**  >  **hinzufügen".**
2. Geben Sie **im Feld Eine Domäne eingeben,** die Sie besitzen, den FQDN der Basisdomäne ein. Im folgenden Beispiel ist die Basisdomäne *customers.adatum.biz.*

    ![Screenshot der Seite "Domäne hinzufügen"](media/direct-routing-2-sbc-add-domain.png)

3. Klicken Sie auf **Weiter**.
4. Im Beispiel verfügt der Mandant bereits adatum.biz als bestätigter Domänenname. Der Assistent fordert keine zusätzliche Überprüfung an, da customers.adatum.biz eine Unterdomäne für den bereits registrierten Namen ist. Wenn Sie jedoch einen FQDN hinzufügen, der noch nicht überprüft wurde, müssen Sie den Überprüfungsprozess durchgehen. Der Überprüfungsprozess wird [unten beschrieben.](#add-a-subdomain-to-the-customer-tenant-and-verify-it)

    ![Screenshot mit bestätigung eines bestätigten Domänennamens](media/direct-routing-3-sbc-verify-domain.png)

5. Klicken **Sie auf** Weiter, und wählen Sie auf der Seite Update **DNS-Einstellungen** die Option Ich füge die **DNS-Einträge** selbst hinzu, und klicken Sie auf **Weiter**.
6. Löschen Sie auf der nächsten Seite alle Werte (es sei denn, Sie möchten den Domänennamen für Exchange, SharePoint oder Teams/Skype for Business verwenden), klicken Sie auf Weiter **,** und klicken Sie dann auf **Fertig stellen.** Stellen Sie sicher, dass ihre neue Domäne den Status "Setup abgeschlossen" hat.

    ![Screenshot mit Domänen mit dem Status "Setup abgeschlossen"](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>Aktivieren des Domänennamens

Nachdem Sie einen Domänennamen registriert haben, müssen Sie ihn aktivieren, indem Sie mindestens einen Benutzer mit Einer Telefonsystemlizenz hinzufügen und eine SIP-Adresse mit dem FQDN-Teil der SIP-Adresse zuweisen, der der erstellten Basisdomäne zuzuordnen ist. Die Lizenz kann nach der Domänenaktivierung widerrufen werden (es kann bis zu 24 Stunden dauern).

> [!NOTE]
> Der Netzbetreiber-Mandant muss mindestens eine dem Mandanten zugewiesene Telefonsystemlizenz behalten, um das Entfernen der Skype for Business-Konfiguration zu vermeiden. 

*Weitere Informationen zum Hinzufügen von Benutzern in Microsoft 365- oder Office 365-Organisationen finden Sie unter Hilfe zu [Microsoft 365- oder Office 365-Domänen.](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)*

Beispiel: test@customers.adatum.biz

![Screenshot der Aktivierungsseite der Basisdomäne](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrieren eines Unterdomänennamens in einem Kunden mandanten

Sie müssen für jeden Kunden einen eindeutigen Unterdomänennamen erstellen. In diesem Beispiel erstellen wir eine Unterdomäne sbc1.customers.adatum.biz in einem Mandanten mit dem Standarddomänennamen woodgrovebank.us.

**Alle folgenden Aktionen befinden sich im Kunden-Mandanten.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Sicherstellen, dass Sie über die entsprechenden Rechte im Kunden-Mandanten verfügen

Sie können neue Domänen nur hinzufügen, wenn Sie sich beim Microsoft 365 Admin Center als globaler Administrator angemeldet haben. 

Um die rolle zu überprüfen, die Sie haben, melden Sie sich bitte beim Microsoft 365 Admin Center an ( , wechseln Sie zu Aktive Benutzer , und überprüfen Sie dann, ob Sie über eine Rolle des globalen https://portal.office.com)   >  Administrators verfügen. 

Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Microsoft 365 oder Office 365 finden Sie unter [Informationen zu Administratorrollen.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Hinzufügen einer Unterdomäne zum Kunden-Mandanten und Überprüfen
1. Wechseln Sie im Microsoft 365 Admin Center zu **Domäne**  >  **"Domänen**  >  **hinzufügen".**
2. Geben Sie **im Feld Domäne eingeben, die** Sie besitzen, den FQDN der Unterdomäne für diesen Mandanten ein. Im folgenden Beispiel ist die Unterdomäne sbc1.customers.adatum.biz.

    ![Screenshot der Seite "Domäne hinzufügen"](media/direct-routing-5-sbc-add-customer-domain.png)

3. Klicken Sie auf **Weiter**.
4. Der FQDN wurde noch nie im Mandanten registriert. Im nächsten Schritt müssen Sie die Domäne überprüfen. Wählen **Sie stattdessen Hinzufügen eines TXT-Eintrags aus.** 

    ![Screenshot der Seite Domäne überprüfen](media/direct-routing-6-sbc-verify-customer-domain.png)

5. Klicken **Sie auf Weiter**, und notieren Sie sich den generierten TXT-Wert, um den Domänennamen zu überprüfen.

    ![Screenshot von Texteinträgen auf der Seite Domäne überprüfen](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Erstellen Sie den TXT-Eintrag mit dem Wert aus dem vorherigen Schritt des DNS-Hostinganbieters des Netzbetreibers.

    ![Screenshot zum Erstellen des TXT-Eintrags](media/direct-routing-8-sbc-txt-record.png)

    Weitere Informationen finden Sie unter [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter.](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)

7. Wechseln Sie zurück zum Microsoft 365 Admin Center des Kunden, und klicken Sie auf **Überprüfen.** 
8. Wählen Sie auf der nächsten Seite Ich füge die **DNS-Einträge** selbst hinzu, und klicken Sie auf **Weiter.**

    ![Screenshot der Optionen auf der Seite "Update DNS-Einstellungen"](media/direct-routing-9-sbc-update-dns.png)

9. Löschen Sie **auf der Seite Onlinedienste auswählen** alle Optionen, und klicken Sie auf **Weiter.**

    ![Screenshot der Seite "Onlinedienste auswählen"](media/direct-routing-10-sbc-choose-services.png)

10. Klicken **Sie auf der** Seite Update **DNS-Einstellungen auf** Fertig stellen.

    ![Screenshot der Seite "Update DNS-Einstellungen"](media/direct-routing-11-sbc-update-dns-finish.png)

11. Stellen Sie sicher, dass der Status **Setup abgeschlossen ist.** 
    
    ![Screenshot der Seite mit dem Status "Setup abgeschlossen"](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> Die Basis-URL und die Unterdomäne für den einzelnen Client müssen sich auf demselben Mandanten besennen, damit Sie einen direkten _Routenstamm hinzufügen_ können.

### <a name="activate-the-subdomain-name"></a>Aktivieren des Unterdomänennamens

Nachdem Sie einen Domänennamen registriert haben, müssen Sie ihn aktivieren, indem Sie mindestens einen Benutzer hinzufügen und eine SIP-Adresse mit dem FQDN-Teil der SIP-Adresse zuweisen, der der erstellten Unterdomäne im Kunden-Mandanten zuzuordnen ist. Die Lizenz kann vom Benutzer nach der Aktivierung der Unterdomäne widerrufen werden (es kann bis zu 24 Stunden dauern).

*Weitere Informationen zum Hinzufügen von Benutzern in Microsoft 365- oder Office 365-Organisationen finden Sie unter Hilfe zu [Microsoft 365- oder Office 365-Domänen.](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)*

Beispiel: test@sbc1.customers.adatum.biz

![Screenshot der Aktivierung der Seite "Unterdomäne"](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Erstellen eines Trunks und Bereitstellen von Benutzern

Mit der ersten Version von Direct Routing musste microsoft jedem bedienten Mandanten (Kundenmandant) mithilfe von New-CSOnlinePSTNGateway einen Trunk hinzufügen.

Dies hat sich jedoch aus zwei Gründen nicht als optimal erwiesen:
 
- **Verwaltungsaufwand**. Durch das Ausladen oder Entladen eines SBC werden beispielsweise einige Parameter geändert, z. B. das Aktivieren oder Deaktivieren der Medienumgehung. Das Ändern des Ports erfordert das Ändern von Parametern in mehreren Mandanten (durch Ausführen von Set-CSOnlinePSTNGateway), ist aber tatsächlich der gleiche SBC. 

-  **Overheadverarbeitung**. Sammeln und Überwachen von Trunkzustandsdaten – SIP-Optionen, die aus mehreren logischen Trunks gesammelt werden, die in Wirklichkeit der gleiche SBC und der gleiche physische Trunk sind, verlangsamen die Verarbeitung der Routingdaten.
 
Basierend auf diesem Feedback bringt Microsoft eine neue Logik zum Bereitstellen der Trunks für die Kunden-Mandanten ein.

Es wurden zwei neue Entitäten eingeführt:
-    Ein Im Netzbetreiber-Mandant registrierter Netzbetreiberstamm mit dem Befehl New-CSOnlinePSTNGateway, z. B. New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.

-    Ein abgeleiteter Trunk, für den keine Registrierung erforderlich ist. Es ist einfach ein gewünschter Hostname, der aus dem Carrier Trunk hinzugefügt wird. Er leitet alle Konfigurationsparameter vom Netzbetreiberstamm ab. Der abgeleitete Trunk muss in PowerShell nicht erstellt werden, und die Zuordnung mit dem Carrier Trunk basiert auf dem FQDN-Namen (siehe Details unten).

**Bereitstellungslogik und Beispiel**

-    Netzbetreiber müssen nur einen einzigen Trunk (Carrier Trunk in der Domäne des Netzbetreibers) mithilfe des Befehls Set-CSOnlinePSTNGateway verwalten. Im obigen Beispiel ist adatum.biz;
-    Im Kunden-Mandanten muss der Netzbetreiber nur den abgeleiteten Stamm FQDN zu den Sprachroutingrichtlinien der Benutzer hinzufügen. Es ist nicht nötig, New-CSOnlinePSTNGateway für einen Trunk ausführen.
-    Der abgeleitete Trunk erbt oder leitet, wie der Name schon sagt, alle Konfigurationsparameter vom Carrier Trunk ab. Beispiele:
-    Customers.adatum.biz – der Carrier Trunk, der im Carrier Tenant erstellt werden muss.
-    Sbc1.customers.adatum.biz – der abgeleitete Trunk in einem Kunden-Mandant, der nicht in PowerShell erstellt werden muss.  Sie können einfach den Namen des abgeleiteten Trunks im Kunden-Mandanten in der Online-Voiceroutingrichtlinie hinzufügen, ohne sie zu erstellen.
-   Carrier muss den DNS-Eintrag einrichten, um die abgeleitete Trunk-FQDN-Adresse an die SBC-Ip-Adresse des Netzbetreibers zu lösen.

-    Alle Änderungen, die an einem Carrier Trunk (beim Carrier Tenant) vorgenommen werden, werden automatisch auf abgeleitete Trunks angewendet. Beispielsweise können Netzbetreiber einen SIP-Port im Netzbetreiberstamm ändern, und diese Änderung gilt für alle abgeleiteten Trunks. Neue Logik zum Konfigurieren der Trunks vereinfacht die Verwaltung, da Sie nicht zu jedem Mandanten wechseln und den Parameter für jeden Trunk ändern müssen.
-    Die Optionen werden nur an den Carrier Trunk FQDN gesendet. Der Integritätsstatus des Netzbetreiberstamms wird auf alle abgeleiteten Trunks angewendet und für Routingentscheidungen verwendet. Hier finden Sie weitere Informationen [zu Den Direct Routing-Optionen.](./direct-routing-monitor-and-troubleshoot.md)
-    Der Netzbetreiber kann den Netzbetreiberstamm ablaufen, und alle abgeleiteten Trunks werden ebenfalls entleert. 
 

**Migration vom vorherigen Modell zum Carrier Trunk**
 
Für die Migration von der aktuellen Implementierung des gehosteten Carriermodells in das neue Modell müssen die Netzbetreiber die Trunks für Kundendächer neu konfigurieren. Entfernen Sie die Trunks von den Kunden-Mandanten mithilfe Remove-CSOnlinePSTNGateway (den Trunk im Netzbetreiber-Mandanten verlassen)-

Wir empfehlen dringend, so bald wie möglich zur neuen Lösung zu migrieren, da wir die Überwachung und Bereitstellung mithilfe des Carrier- und abgeleiteten Trunkmodells verbessern werden.
 

Lesen Sie die Anweisungen für [den SBC-Anbieter](#deploy-and-configure-the-sbc) zum Konfigurieren des Sendens des FQDN-Namens von Unterdomänen in der Kontaktüberschrift.

## <a name="considerations-for-setting-up-muti-tenant-failover"></a>Überlegungen zum Einrichten eines Failovers für muti-tenant 

Zum Einrichten eines Failovers für eine Umgebung mit mehreren Mandanten müssen Sie die folgenden Schritte ausführen:

- Fügen Sie für jeden Mandanten die FQDNs für zwei unterschiedliche SBCs hinzu.  Beispiel:

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- Geben Sie in den Online voice routing-Richtlinien der Benutzer beide SBCs an.  Wenn ein SBC fehlschlägt, führt die Routingrichtlinie Anrufe an den zweiten SBC weiter.


## <a name="see-also"></a>Mehr dazu

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)