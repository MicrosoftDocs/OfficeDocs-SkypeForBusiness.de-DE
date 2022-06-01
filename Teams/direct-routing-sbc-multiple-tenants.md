---
title: Konfigurieren des Session Border Controllers – Mehrere Mandanten
ms.reviewer: filippse
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
description: Erfahren Sie, wie Sie einen Session Border Controller (SBC) so konfigurieren, dass er mehrere Mandanten für Microsoft-Partner und/oder PSTN-Netzbetreiber bedient.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be75743752f34024baf7b2fd017557c2f0044ba6
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823686"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Konfigurieren eines Session Border Controllers für mehrere Mandanten

Direct Routing unterstützt die Konfiguration eines Session Border Controller (SBC) für mehrere Mandanten.

> [!NOTE]
> Dieses Szenario wurde für Microsoft-Partner und/oder PSTN-Netzbetreiber entwickelt, die später in diesem Dokument als Netzbetreiber bezeichnet werden. Ein Netzbetreiber verkauft Telefoniedienste, die an Microsoft Teams an ihre Kunden geliefert werden. 

Ein Netzbetreiber:
- Stellt einen SBC in seinem Rechenzentrum bereit und verwaltet diesen (Kunden müssen keinen SBC implementieren, und sie erhalten Telefoniedienste vom Netzbetreiber im Teams-Client).
- Verbindet den SBC mit mehreren Mandanten.
- Stellt PSTN-Dienste (Public Switched Telephone Network) für Kunden bereit.
- Verwaltet die Anrufqualität von Ende zu Ende.
- Gebühren separat für PSTN-Dienste.

Microsoft verwaltet keine Netzbetreiber. Microsoft bietet Telefonsystem – eine Nebenstellenanlage (Private Branch Exchange) – und einen Teams-Client an. Microsoft zertifiziert auch Telefone und zertifiziert SBCs, die mit Telefonsystem verwendet werden können. Bevor Sie einen Netzbetreiber auswählen, stellen Sie sicher, dass Ihre Wahl über einen zertifizierten SBC verfügt und die Sprachqualität von Ende zu Ende verwalten kann.

Im Folgenden finden Sie die technischen Implementierungsschritte zum Konfigurieren des Szenarios.

**Nur Netzbetreiber:**
1. Stellen Sie den SBC bereit, und konfigurieren Sie ihn für das Hostingszenario gemäß den [Anweisungen der zertifizierten SBC-Anbieter](#deploy-and-configure-the-sbc).
2. Registrieren Sie einen Basisdomänennamen im Netzbetreibermandanten, und fordern Sie ein Platzhalterzertifikat an.
3. Registrieren Sie eine Unterdomäne für jeden Kunden, die Teil der Basisdomäne ist.

**Netzbetreiber mit einem globalen Kundenadministrator:**
1. Fügen Sie dem Kundenmandanten den Namen der Unterdomäne hinzu.
2. Aktivieren Sie den Namen der Unterdomäne.
3. Konfigurieren Sie den Trunk vom Netzbetreiber zum Kundenmandanten, und stellen Sie Benutzer bereit.

*Stellen Sie sicher, dass Sie die DNS-Grundlagen kennen und wissen, wie der Domänenname in Microsoft 365 verwaltet wird. Weitere [Informationen finden Sie unter Hilfe zu Microsoft 365 Domänen](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider), bevor Sie fortfahren.*

## <a name="deploy-and-configure-the-sbc"></a>Bereitstellen und Konfigurieren des SBC

Ausführliche Schritte zum Bereitstellen und Konfigurieren von SBCs für ein SBC-Hostingszenario finden Sie in der Dokumentation des SBC-Anbieters.

- **Audiocodes:** Informationen zur Konfiguration des SBC-Hostingszenarios finden Sie in den [Anmerkungen zur Direct Routing-Konfiguration](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), wie unter "Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note" beschrieben. 
- **Oracle:** Informationen zur Konfiguration des SBC-Hostingszenarios finden Sie in den [Anmerkungen zur Direct Routing-Konfiguration](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html) , wie im Abschnitt "Microsoft" beschrieben. 
- **Menübandkommunikation:** Dokumentation zum Konfigurieren von SbCs der Ribbon Core-Serie finden Sie unter [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe). Siehe auch [Bewährte Methoden zum Konfigurieren von Netzbetreibern für Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)
- **TE-Systems (anynode):** Registrieren Sie sich auf der [TE-Systems Community-Seite](https://community.te-systems.de/) für Dokumentation und Beispiele zum Konfigurieren von Anynode SBC für mehrere Mandanten.
- **Metaswitch:** Registrieren Sie sich auf der [Seite "Metaswitch Community](https://manuals.metaswitch.com/MAN39555)", um zu dokumentieren, wie Perimeta SBC für mehrere Mandanten aktiviert wird.

> [!NOTE]
> Stellen Sie sicher, dass Sie wissen, wie sie die Kopfzeile "Kontakt" konfigurieren. Der Kontaktkopf wird verwendet, um den Kundenmandanten in der eingehenden Einladungsnachricht zu finden. 

## <a name="register-a-base-domain-and-subdomains"></a>Registrieren einer Basisdomäne und Unterdomänen

Für das Hostingszenario müssen Sie Folgendes erstellen:

- Ein Basisdomänenname im Besitz des Netzbetreibers.
- Eine Unterdomäne, die Teil des Basisdomänennamens in jedem Kundenmandanten ist.

Im folgenden Beispiel:

- Adatum ist ein Netzbetreiber, der mehrere Kunden mit Internet- und Telefoniediensten bedient.
- Woodgrove Bank, Contoso und Adventure Works sind drei Kunden, die über Microsoft 365 Domänen verfügen, aber die Telefoniedienste von Adatum erhalten.

Unterdomänen **MÜSSEN** mit dem FQDN-Namen des Trunks übereinstimmen, der für den Kunden konfiguriert wird, und dem FQDN im Kontaktheader, wenn die Einladung an Microsoft 365 gesendet wird. 

Wenn ein Anruf an der Microsoft 365 Direct Routing-Schnittstelle eingeht, verwendet die Schnittstelle den Kontaktheader, um den Mandanten zu finden, in dem der Benutzer nachschlagen soll. Direct Routing verwendet keine Telefonnummernsuche in der Einladung, da einige Kunden möglicherweise Nicht-DID-Nummern haben, die sich in mehreren Mandanten überlappen können. Daher ist der FQDN-Name im Kontaktheader erforderlich, um den genauen Mandanten zu identifizieren, um den Benutzer anhand der Telefonnummer nachzuschlagen.

*Weitere Informationen zum Erstellen von Domänennamen in Microsoft 365 Organisationen finden [Sie unter Hilfe zu Microsoft 365 Domänen](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).*

Das folgende Diagramm fasst die Anforderungen für die Basisdomäne, Unterdomänen und den Kontaktheader zusammen.

:::image type="content" source="media/direct-routing-1-sbc-requirements.png" alt-text="Diagramm, das die Anforderungen an Domänen und den Kontaktheader zeigt." lightbox="media/direct-routing-1-sbc-requirements.png":::

Der SBC erfordert ein Zertifikat, um die Verbindungen zu authentifizieren. Für das SBC-Hostingszenario muss der Netzbetreiber ein Zertifikat mit CN- und/oder SAN-.base_domain anfordern (z. B. .customers.adatum.biz).For the SBC hosting scenario, the carrier needs to request a certificate with CN and/or SAN *\*.base_domain (for example, \*.customers.adatum.biz)*. Dieses Zertifikat kann verwendet werden, um Verbindungen mit mehreren Mandanten zu authentifizieren, die von einem einzelnen SBC bereitgestellt werden.

Die folgende Tabelle ist ein Beispiel für eine Konfiguration.


|Neuer Domänenname |Typ|Registriert  |Zertifikat-CN/SAN für SBC  |Mandantenstandarddomäne im Beispiel  |FQDN-Name, den SBC beim Senden von Anrufen an Benutzer im Kontaktheader enthalten muss|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Basis     |     Im Netzbetreibermandanten  |    \*.customers.adatum.biz  |   adatum.biz      |NA, dies ist ein Dienstmandant, keine Benutzer |
|sbc1.customers.adatum.biz|    Subdomain  |    In einem Kundenmandanten  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Subdomain | In einem Kundenmandanten   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Subdomain | In einem Kundenmandanten |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |

Führen Sie die unten beschriebenen Schritte aus, um die Basis- und Unterdomänen zu konfigurieren. In diesem Beispiel werden ein Basisdomänenname (customers.adatum.biz) und eine Unterdomäne für einen Kunden (sbc1.customers.adatum.biz im Woodgrove Bank-Mandanten) konfiguriert.

> [!NOTE]
> Verwenden Sie sbcX.customers.adatum.biz, um VoIP im Netzbetreibermandanten zu aktivieren; sbcX kann ein beliebiger eindeutiger und gültiger alphanumerischer Hostname sein.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registrieren eines Basisdomänennamens im Netzbetreibermandanten

**Diese Aktionen werden im Netzbetreibermandanten ausgeführt.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Stellen Sie sicher, dass Sie über die entsprechenden Rechte im Netzbetreibermandanten verfügen.

Sie können neue Domänen nur hinzufügen, wenn Sie sich bei der Microsoft 365 Admin Center als globaler Administrator angemeldet haben. 

Um die Rolle zu überprüfen, die Sie haben, melden Sie sich bei der Microsoft 365 Admin Center an (https://portal.office.com)wechseln Sie zu **"Aktive Benutzer**" für **Benutzer** > , und vergewissern Sie sich dann, dass Sie über eine rolle "Globaler Administrator" verfügen. 

Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Microsoft 365 finden Sie unter ["Informationen zu Administratorrollen"](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Hinzufügen einer Basisdomäne zum Mandanten und Überprüfen der Domäne

1. Wechseln Sie in der Microsoft 365 Admin Center zu **"Domäne****hinzufügen" für Setupdomänen** >  > .

2. **Geben Sie im Feld "Domäne eingeben, die Sie besitzen**" den FQDN der Basisdomäne ein. Im folgenden Beispiel wird die Basisdomäne *customers.adatum.biz*.

3. Klicken Sie auf **Weiter**.

4. In diesem Beispiel hat der Mandant bereits adatum.biz als bestätigten Domänennamen. Der Assistent fordert keine zusätzliche Überprüfung an, da customers.adatum.biz eine Unterdomäne für den bereits registrierten Namen ist. Wenn Sie jedoch einen FQDN hinzufügen, der noch nicht überprüft wurde, müssen Sie den Überprüfungsprozess durchlaufen. Der Prozess der Überprüfung wird [unten beschrieben](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

5. Wählen Sie **"Weiter**" aus, und wählen Sie auf der Seite **"DNS-Einstellungen aktualisieren**" **die Option "Ich füge die DNS-Einträge selbst hinzu**" und dann **"Weiter**".

6. Löschen Sie auf der nächsten Seite alle Werte (es sei denn, Sie möchten den Domänennamen für Exchange, SharePoint, Teams oder Skype for Business verwenden), wählen Sie **"Weiter**" und dann "**Fertig stellen**" aus. Vergewissern Sie sich, dass ihre neue Domäne den Status "Setup abgeschlossen" hat.

### <a name="activate-the-domain-name"></a>Aktivieren des Domänennamens

Nachdem Sie einen Domänennamen registriert haben, müssen Sie ihn aktivieren, indem Sie mindestens einen Benutzer mit einer Telefonsystem Lizenz hinzufügen und eine SIP-Adresse mit dem FQDN-Teil der SIP-Adresse zuweisen, der der erstellten Basisdomäne entspricht.

> [!NOTE]
> Der Netzbetreibermandant muss mindestens eine dem Mandanten zugewiesene Telefonsystem Lizenz behalten, um das Entfernen der Skype for Business-Konfiguration zu vermeiden. 

*Weitere Informationen zum Hinzufügen von Benutzern in Microsoft 365 Organisationen finden [Sie unter Hilfe zu Microsoft 365 Domänen](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).*

Beispiel: test@customers.adatum.biz

![Screenshot der Basisdomänenaktivierungsseite.](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrieren eines Unterdomänennamens in einem Kundenmandanten

Sie müssen für jeden Kunden einen eindeutigen Unterdomänennamen erstellen. In diesem Beispiel erstellen wir eine Unterdomäne sbc1.customers.adatum.biz in einem Mandanten mit dem Standarddomänennamen woodgrovebank.us.

**Alle unten aufgeführten Aktionen befinden sich im Kundenmandanten.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Stellen Sie sicher, dass Sie über die entsprechenden Rechte im Kundenmandanten verfügen.

Sie können neue Domänen nur hinzufügen, wenn Sie sich bei der Microsoft 365 Admin Center als globaler Administrator angemeldet haben. 

Um die Rolle zu überprüfen, die Sie haben, melden Sie sich bei der Microsoft 365 Admin Center an (https://portal.office.com)wechseln Sie zu **"Aktive Benutzer**" für **Benutzer** > , und vergewissern Sie sich dann, dass Sie über eine rolle "Globaler Administrator" verfügen. 

Weitere Informationen zu Administratorrollen und zum Zuweisen einer Rolle in Microsoft 365 finden Sie unter ["Informationen zu Administratorrollen"](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Hinzufügen einer Unterdomäne zum Kundenmandanten und Überprüfen der Domäne

1. Wechseln Sie in der Microsoft 365 Admin Center zu **"Domäne****hinzufügen" für Setupdomänen** >  > .

2. **Geben Sie im Feld "Domäne eingeben, die Sie besitzen**" den FQDN der Unterdomäne für diesen Mandanten ein. Im folgenden Beispiel wird die Unterdomäne sbc1.customers.adatum.biz.

3. Wählen Sie **"Weiter**" aus.

4. Der FQDN wurde nie im Mandanten registriert. Im nächsten Schritt müssen Sie die Domäne überprüfen. Wählen Sie **stattdessen "TXT-Eintrag hinzufügen" aus**. 

5. Wählen Sie **"Weiter**" aus, und notieren Sie sich den txt-Wert, der generiert wurde, um den Domänennamen zu überprüfen.

    ![Screenshot von Texteinträgen auf der Seite "Domäne überprüfen".](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Erstellen Sie den TXT-Eintrag mit dem Wert aus dem vorherigen Schritt im DNS-Hostinganbieter des Netzbetreibers.

    Weitere Informationen finden [Sie unter Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Wechseln Sie zum Microsoft 365 Admin Center des Kunden, und wählen Sie **"Überprüfen"** aus. 

8. Wählen Sie auf der nächsten Seite **die Option "Ich füge die DNS-Einträge selbst hinzu** " und dann **"Weiter**" aus.

9. Deaktivieren Sie auf der Seite **"Onlinedienste auswählen**" alle Optionen, und wählen Sie **"Weiter**" aus.

10. Wählen Sie auf der Seite **"DNS-Einstellungen aktualisieren**" die Option "**Fertig stellen**" aus.

11. Stellen Sie sicher, dass der Status **"Setup abgeschlossen**" ist. 
    
    ![Screenshot der Seite mit dem Status "Setup abgeschlossen".](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> Die Basis-URL und die Unterdomäne für den einzelnen Client müssen sich auf demselben Mandanten befinden, damit Sie einen _direkten Routentrunk_ hinzufügen können.

### <a name="activate-the-subdomain-name"></a>Aktivieren des Unterdomänennamens

Nachdem Sie einen Domänennamen registriert haben, müssen Sie ihn aktivieren, indem Sie mindestens einen Benutzer hinzufügen und eine SIP-Adresse mit dem FQDN-Teil der SIP-Adresse zuweisen, der der erstellten Unterdomäne im Kundenmandanten entspricht. 

*Weitere Informationen zum Hinzufügen von Benutzern in Microsoft 365 Organisationen finden [Sie unter Hilfe zu Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).*

Beispiel: test@sbc1.customers.adatum.biz

![Screenshot der Seite "Aktivierung der Unterdomäne".](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Erstellen eines Trunks und Bereitstellen von Benutzern

Mit der ersten Version von Direct Routing musste Microsoft jedem bedienten Mandanten (Kundenmandanten) mithilfe des cmdlets New-CSOnlinePSTNGateway einen Trunk hinzufügen.

Diese Methode hat sich jedoch aus zwei Gründen als nicht optimal erwiesen:
 
- **Overhead-Verwaltung**. Durch das Auslagern oder Entleeren eines SBC werden beispielsweise einige Parameter geändert, z. B. das Aktivieren oder Deaktivieren der Medienumgehung. Das Ändern des Ports erfordert das Ändern von Parametern in mehreren Mandanten (durch Ausführen von Set-CSOnlinePSTNGateway), ist aber tatsächlich derselbe SBC. 

-  **Mehraufwand bei der Verarbeitung**. Sammeln und Überwachen von Trunkintegritätsdaten – SIP-Optionen, die aus mehreren logischen Trunks gesammelt werden, die in Wirklichkeit der gleiche SBC und derselbe physische Trunk sind, verlangsamen die Verarbeitung der Routingdaten.
 
Basierend auf diesem Feedback bringt Microsoft eine neue Logik ein, um die Trunks für die Kundenmandanten bereitzustellen.

Es wurden zwei neue Entitäten eingeführt:

- Ein Im Netzbetreibermandanten registrierter Netzbetreiber-Trunk mithilfe des Befehls New-CSOnlinePSTNGateway. Zum Beispiel:  
   
   ```PowerShell
   New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true
    ```

- Ein abgeleiteter Trunk, für den keine Registrierung erforderlich ist. Es ist einfach ein gewünschter Hostname, der vom Netzbetreibertrunk hinzugefügt wird. Er leitet alle Konfigurationsparameter vom Netzbetreibertrunk ab. Der abgeleitete Trunk muss nicht in PowerShell erstellt werden, und die Zuordnung zum Netzbetreibertrunk basiert auf dem FQDN-Namen (siehe Details unten).

**Bereitstellungslogik und Beispiel**

- Netzbetreiber müssen nur einen einzigen Trunk (den Netzbetreibertrunk in der Netzbetreiberdomäne) mithilfe des Befehls Set-CSOnlinePSTNGateway einrichten und verwalten. Im obigen Beispiel ist es adatum.biz.

- Im Kundenmandanten muss der Netzbetreiber den abgeleiteten Trunk-FQDN zu den VoIP-Routen hinzufügen. Es ist nicht erforderlich, New-CSOnlinePSTNGateway für einen Trunk auszuführen.

- Der abgeleitete Trunk erbt oder leitet, wie der Name schon sagt, alle Konfigurationsparameter vom Netzbetreibertrunk ab. 

Beispiele:
- Customers.adatum.biz – der Netzbetreibertrunk, der im Netzbetreibermandanten erstellt werden muss.

- Sbc1.customers.adatum.biz – der abgeleitete Trunk in einem Kundenmandanten, der nicht in PowerShell erstellt werden muss. Sie können den Namen des abgeleiteten Trunks im Kundenmandanten in der Online-VoIP-Routingrichtlinie hinzufügen, ohne ihn zu erstellen (verwenden Sie den abgeleiteten Trunk-FQDN beim Einrichten der VoIP-Routingrichtlinie in TAC unter Teams-Voice-Direct Routing-Voice Routes field SBCs enrolled).

- Der Netzbetreiber muss einen DNS-Eintrag einrichten, der den abgeleiteten Trunk-FQDN für die SBC-IP-Adresse des Netzbetreibers auflöst.

- Alle an einem Netzbetreibertrunk (im Netzbetreibermandanten) vorgenommenen Änderungen werden automatisch auf abgeleitete Trunks angewendet. Netzbetreiber können z. B. einen SIP-Port auf dem Netzbetreibertrunk ändern, und diese Änderung gilt für alle abgeleiteten Trunks. Die neue Logik zum Konfigurieren der Trunks vereinfacht die Verwaltung, da Sie nicht zu jedem Mandanten wechseln und den Parameter für jeden Trunk ändern müssen.

- Die Optionen werden nur an den Netzbetreiber-Trunk-FQDN gesendet. Der Integritätsstatus des Netzbetreibertrunks wird auf alle abgeleiteten Trunks angewendet und für Routingentscheidungen verwendet. Erfahren Sie mehr über [Direct Routing-Optionen](./direct-routing-monitor-and-troubleshoot.md).

- Der Netzbetreiber kann den Trägertrunk entleeren, und alle abgeleiteten Trunks werden ebenfalls entleert. 
 
> [!NOTE]
> Auf den Netzbetreibertrunk angewendete Übersetzungsregeln für Nummern gelten nicht für abgeleitete Trunks. Dies ist ein bekanntes Problem. Als alternative Lösung müssen Übersetzungsregeln für Nummern für den Mandanten jedes Kunden erstellt werden.

**Migration vom vorherigen Modell zum Netzbetreibertrunk**
 
Für die Migration von der aktuellen Implementierung des vom Netzbetreiber gehosteten Modells zum neuen Modell müssen die Netzbetreiber die Trunks für Kundenmandanten neu konfigurieren. Entfernen Sie die Trunks aus den Kundenmandanten mithilfe von Remove-CSOnlinePSTNGateway (den Trunk im Netzbetreibermandanten verlassen)-

Wir empfehlen dringend, so schnell wie möglich zu der neuen Lösung zu migrieren, da wir die Überwachung und Bereitstellung mithilfe des Netzbetreibers und des abgeleiteten Trunkmodells verbessern werden.
 
Weitere Informationen zum Konfigurieren des Sendens des FQDN-Namens von Unterdomänen im Kontaktheader finden Sie in den [Anweisungen des SBC-Anbieters](#deploy-and-configure-the-sbc).

## <a name="considerations-for-setting-up-multi-tenant-failover"></a>Überlegungen zum Einrichten eines Failovers mit mehreren Mandanten 

Um ein Failover für eine Umgebung mit mehreren Mandanten einzurichten, müssen Sie die folgenden Schritte ausführen:

- Fügen Sie für jeden Mandanten die FQDNs für zwei verschiedene SBCs hinzu. Zum Beispiel: 

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- Geben Sie in den Online-VoIP-Routen beide SBCs an. Wenn ein SBC fehlschlägt, leitet die Routingrichtlinie Anrufe an den zweiten SBC weiter.


## <a name="see-also"></a>Siehe auch

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)
