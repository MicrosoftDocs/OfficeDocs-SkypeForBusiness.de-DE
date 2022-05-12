---
title: Konfigurieren des SIP-Gateways
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Erfahren Sie, wie Sie das SIP-Gateway konfigurieren.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 72fdabd1ba25254876bc3d4506c889d50cbc6613
ms.sourcegitcommit: cd9a1f7afaaf053741c81022e7052bf6f8008fcc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2022
ms.locfileid: "65370888"
---
# <a name="configure-sip-gateway"></a>Konfigurieren des SIP-Gateways

In diesem Artikel wird erläutert, wie Sie das SIP-Gateway so konfigurieren, dass Ihre Organisation kompatible SIP-Geräte mit Microsoft Teams verwenden kann. Informationen dazu, was das SIP-Gateway für Ihre Organisation leisten kann und welche Hardware, Software und Lizenzen Ihre Organisation dafür benötigt, finden Sie unter ["Planen des SIP-Gateways](sip-gateway-plan.md)".

Bevor Sie das SIP-Gateway konfigurieren können, gehen Sie folgendermaßen vor:

- **Setzen Sie SIP-Geräte auf die Standardeinstellungen der Werkseinstellungen zurück.** Sie oder die Benutzer Ihrer Organisation müssen jedes sip-Gerät, das mit dem SIP-Gateway verwendet wird, auf die Werksstandardeinstellungen zurücksetzen. Informationen dazu finden Sie in den Anweisungen des Herstellers.

- **Öffnen Sie Ihre Firewall, um Microsoft 365 und Teams.** Öffnen Sie die Firewall Ihres Netzwerks, um Datenverkehr zu Microsoft 365 und Teams, wie in [Office 365 URLs und IP-Adressbereichen](/microsoft-365/enterprise/urls-and-ip-address-ranges) beschrieben. Firewallregeln sind nur für ausgehenden Datenverkehr erforderlich.

- **Stellen Sie sicher, dass sich die SIP-Geräte nicht hinter einem Proxy befinden.** Stellen Sie sicher, dass der HTTP/s-Datenverkehr jeden http/s-Proxy des Unternehmens umgeht.

- **Öffnen Sie den UDP-Port.** Open UDP port in the range 49152 to 53247 for IP ranges 52.112.0.0/14 and 52.120.0.0/14.

- **Öffnen Sie den TCP-Port.** Öffnen Sie den TCP-Port 5061 für die IP-Bereiche 52.112.0.0/14 und 52.120.0.0/14.

- **Öffnen Sie die folgenden HTTPS-Endpunkte (IP-Adressen und URLs):**

  - 13.75.175.145
  - 52.189.219.201
  - 51.124.34.164
  - 13.74.250.91
  - 13.83.55.36
  - 23.96.103.40
  - https://blobsdgapac.blob.core.windows.net
  - https://blobsdgemea.blob.core.windows.net
  - https://blobsdgnoam.blob.core.windows.net
  - https://httpblobsdgapac.blob.core.windows.net
  - https://httpblobsdgemea.blob.core.windows.net
  - https://httpblobsdgnoam.blob.core.windows.net



In den folgenden Abschnitten wird beschrieben, was Sie als Administrator tun müssen, um das SIP-Gateway zu konfigurieren.

- [Stellen Sie sicher, dass das SIP-Gateway für Ihre Organisation verfügbar ist](#verify-that-sip-gateway-is-available-for-your-organization).

- [Aktivieren Sie das SIP-Gateway für die Benutzer in Ihrer Organisation](#enable-sip-gateway-for-the-users-in-your-organization).

- [Legen Sie die URL des SIP-Gatewaybereitstellungsservers fest](#set-the-sip-gateway-provisioning-server-url).

In diesem Artikel wird auch beschrieben, wie Sie:

- [Registrieren Sie SIP-Geräte entweder einzeln oder in Batches, um Dies zu erleichtern](#provision-and-enroll-sip-devices-as-common-area-phones).  


- [Zeigen Sie Ihre SIP-Geräte an und überwachen Sie sie.](#view-and-monitor-sip-devices)

- [Aktivieren Sie die Unterstützung für eine mehrsprachige Benutzeroberfläche.](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>Stellen Sie sicher, dass das SIP-Gateway für Ihre Organisation verfügbar ist.

1. Melden Sie sich beim [Teams Admin Center](https://admin.teams.microsoft.com/) an.

2. Wählen Sie links **Teams Geräte** aus, und überprüfen Sie, ob die Registerkarte "**SIP-Geräte**" angezeigt wird. Falls ja, ist der SIP-Gatewaydienst für Ihre Organisation aktiviert.

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>Aktivieren des SIP-Gateways für die Benutzer in Ihrer Organisation

Sie können das SIP-Gateway für Ihre Organisation auf zwei Arten aktivieren: mithilfe des Teams Admin Centers oder mithilfe eines PowerShell-Cmdlets.

### <a name="by-using-teams-admin-center"></a>Mit Teams Admin Center

Führen Sie die folgenden Schritte aus, um das SIP-Gateway im Teams Admin Center zu aktivieren:

1. Wechseln Sie zum [Teams Admin Center](https://admin.teams.microsoft.com/)

2. Wählen Sie links unter **"VoIP**" **die Option "Anrufrichtlinien" aus**.

3. Wählen Sie rechts unter **"Richtlinien verwalten**" die entsprechende Anrufrichtlinie aus, die Benutzern zugewiesen ist, oder erstellen Sie bei Bedarf eine neue Anrufrichtlinie, und weisen Sie sie den erforderlichen Benutzern zu.

4. Wählen Sie **"Richtlinien verwalten**", dann eine Richtlinie und dann **"Bearbeiten"** aus.

5. Aktivieren Sie die Einstellung für **SIP-Geräte, die für Anrufe verwendet werden können**, und wählen Sie dann **"Speichern"** aus.


### <a name="by-using-powershell"></a>Verwenden von PowerShell

Sie können das SIP-Gateway auch mithilfe des PowerShell [Set-CsTeamsCallingPolicy-Cmdlets](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) aktivieren. Um Benutzer für SIP-Geräte zu aktivieren, wählen Sie eine Richtlinie aus, und legen Sie das `-AllowSIPDevicesCalling` Attribut auf `True`. Der Standardwert lautet `False`, sodass Benutzer ihre SIP-Geräte nur verwenden können, wenn Sie sie aktivieren.

> [!NOTE]
> - Die Richtlinienverteilung kann bis zu 24 Stunden dauern.

## <a name="set-the-sip-gateway-provisioning-server-url"></a>Festlegen der URL des SIP-Gatewaybereitstellungsservers

Sie können die URL des SIP-Gatewaybereitstellungsservers in Ihrem DHCP-Server (Dynamic Host Configuration Protocol) festlegen. Benutzer, die remote arbeiten, müssen sie manuell konfigurieren.

### <a name="using-dhcp"></a>Verwenden von DHCP

Legen Sie für jedes SIP-Gerät eine der folgenden SIP-Gateway-Bereitstellungsserver-URLs fest: 

- EMEA: `http://emea.ipp.sdg.teams.microsoft.com`
- Americas: `http://noam.ipp.sdg.teams.microsoft.com`
- APAC: `http://apac.ipp.sdg.teams.microsoft.com`

Fügen Sie Ihrer Teams Organisation SIP-Geräte hinzu, indem Sie die oben genannte URL des SIP-Gatewaybereitstellungsservers in Ihrem DHCP-Server konfigurieren. Weitere Informationen zum DHCP-Server finden Sie [unter Bereitstellen und Verwalten von DHCP](/learn/modules/deploy-manage-dynamic-host-configuration-protocol). Außerdem können Sie DHCP-Option 42 verwenden, um den NTP-Server (Network Time Protocol) und DHCP-Option 2 anzugeben, um den Offset von utc (Coordinated Universal Time) in Sekunden anzugeben. Die Geräte in Ihrer Organisation werden an den SIP-Gatewaybereitstellungsserver weitergeleitet. Erfolgreich bereitgestellte SIP-Telefone zeigen das Teams Logo und eine soft-Taste für die Anmeldung an.

Stellen Sie sicher, dass SIP-Geräte die mindestens unterstützte Firmwareversion für das Onboarding verwenden. Während des Onboardings überträgt das SIP-Gateway die Standardkonfigurations- und Authentifizierungsbenutzeroberfläche an das Gerät. Informationen zur erforderlichen Firmwareversion für SIP-Geräte finden Sie unter [Planen des SIP-Gateways](sip-gateway-plan.md).

### <a name="manually"></a>Manuell

Benutzer, die remote arbeiten, müssen die URL des Bereitstellungsservers manuell auf ihrem SIP-Gerät konfigurieren, indem sie die folgenden Schritte ausführen:

1. Öffnen **Sie Einstellungen** auf dem Gerät, und rufen Sie die IP-Adresse des Geräts ab.

2. Öffnen Sie ein Browserfenster, geben Sie die IP-Adresse des Geräts ein, melden Sie sich an (falls erforderlich), und konfigurieren Sie die URL des Bereitstellungsservers im Webdienstprogramm des Geräts.

3. Geben Sie unter **Einstellungen** oder **den erweiterten Einstellungen** für das Webdienstprogramm die oben gezeigte URL des Bereitstellungsservers ein.

> [!NOTE]
> - Nur kompatible SIP-Geräte können in das SIP-Gateway integriert werden. 
> - Cisco-IP-Telefone müssen in multiplatform-Firmware ge flasht werden, bevor sie integriert werden können. Weitere Informationen hierzu finden Sie im [Cisco Firmware Konvertierungshandbuch](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html).
> - Verwenden Sie für Yealink-Telefone Option 66.
> - Verwenden Sie für Cisco-, Poly- und AudioCode-Telefone Option 160. 
> - Fügen Sie für Cisco-Geräte **/$PSN.xml** an die URL des Bereitstellungsservers an.


## <a name="configure-conditional-access"></a>Konfigurieren des bedingten Zugriffs

Der bedingte Zugriff ist ein Azure Active Directory-Feature (Azure AD), mit dem sichergestellt wird, dass Geräte, die auf Ihre Microsoft 365 Ressourcen zugreifen, ordnungsgemäß verwaltet und sicher sind. SIP-Gateway authentifiziert SIP-Geräte mit Azure AD. Wenn Ihre Organisation also bedingten Zugriff für Geräte im Unternehmensnetzwerk verwendet, sollte es die folgenden IP-Adressen ausschließen:

- Nordamerika:
    - Ost-USA: 52.170.38.140
    - Westen USA: 40.112.144.212
-   REGION EMEA:
    - Nord-EU: 40.112.71.149
    - West-EU: 40.113.112.67
-   Region APAC:
    - Australien Ost: 20.92.120.71
    - Australien Südosten: 13.73.115.90

Weitere Informationen finden Sie unter [IP-Adressbereiche](/azure/active-directory/conditional-access/location-condition#ip-address-ranges).


## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>Bereitstellen und Registrieren von SIP-Geräten als Telefone für gemeinsame Bereiche
> [!NOTE]
> Ein SIP-Gerät muss in das SIP-Gateway integriert werden, bevor es registriert werden kann.

Um Ihre Aufgaben zu optimieren, können Sie SIP-Geräte entweder einzeln oder in Batches im Teams Admin Center registrieren. Dazu gehen Sie so vor:

1. Melden Sie sich beim [**Teams Admin Center**](https://admin.teams.microsoft.com) an.

2. Wählen Sie **Teams** **GeräteSIP-Geräte** >  aus.

3. Wählen Sie oben rechts **"****ActionsProvision-Geräte** > " aus, und führen Sie einen der folgenden Schritte aus:

  - **So stellen Sie ein Gerät bereit:**

     a. Wählen Sie unter **"Auf Aktivierung warten**" die Option **"Hinzufügen"** aus.

     b. Geben Sie im Bereich **"MAC-Adressen hinzufügen** " die **MAC-Adresse** und den **Speicherort** des Geräts ein, und wählen Sie dann **"Übernehmen"** aus.
     
     c. Wählen Sie unter **"Auf Aktivierung warten**" das Gerät aus, das Sie soeben hinzugefügt haben, und wählen Sie dann " **Überprüfungscode generieren"** aus.
     
     d. Notieren Sie sich im Bereich **"Bereitstellungsgeräte** " unter **"Überprüfungscode**" den Überprüfungscode für das SIP-Gerät.

   - **So stellen Sie viele Geräte bereit:**

     a. Wählen Sie **unter "Auf Aktivierung warten**" rechts die Option **"Exportieren**" (das Symbol Microsoft Excel) aus.
     
     b. Wählen Sie im Bereich **"Bereitstellungsgeräte**" unter **Hochladen mehreren MAC-Adressen** **die Option "Vorlage herunterladen"** aus.
     
     c. Speichern Sie **Template_Provisioning.csv** auf Ihrem Computer, und geben Sie die **Felder "MAC-ID"** und " **Speicherort"** ein.
    
     d. Wählen Sie im Bereich "**Bereitstellungsgeräte**" **Hochladen mehrere MAC-Adressen** aus. 

     E. Wählen Sie rechts im **Bereich Hochladen MAC-Adressen** die **Option "Datei auswählen**" und dann die **Template_Provisioning.csv** Datei aus, die Ihre Daten enthält.

     F. Wählen Sie im Bereich **"Bereitstellungsgeräte** " unter **"Bei Aktivierung warten**" ein Gerät aus, und wählen Sie dann " **Überprüfungscode generieren** " aus, um einen einmaligen Überprüfungscode für jedes bereitgestellte Gerät zu generieren. Beachten Sie den Überprüfungscode für jedes SIP-Gerät.

4. Wählen Sie auf dem SIP-Gerät den Registrierungsfeaturecode gefolgt vom Überprüfungscode. Wählen Sie auf dem SIP-Gerät den Registrierungsfeaturecode \*55* (vom SIP-Gateway für die einmalige Überprüfung des Registrierungscodes verwendet), gefolgt von dem Überprüfungscode, der in Teams Admin Center für dieses bestimmte Gerät generiert wird. Wenn der Überprüfungscode beispielsweise 123456 ist, wählen Sie \*55\* 123456, um das Gerät zu registrieren.

5.  Wählen Sie im Bereich **"Bereitstellungsgeräte** " unter **"Auf Anmeldung warten**" die Option " **Abgemeldet" aus**.

6. Kopieren oder notieren Sie sich im Dialogfeld " **Anmelden bei einem Benutzer** " den Kopplungscode des SIP-Geräts.

7. Wechseln Sie zu [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin), und **geben Sie unter "Code eingeben**" den Kopplungscode des SIP-Geräts ein, und wählen Sie dann **"Weiter**" aus.

8. Geben **Sie auf der Microsoft-Anmeldeseite** im Feld **"E-Mail" oder "Telefon** " die E-Mail-Adresse für das SIP-Gerät ein, und wählen Sie dann **"Weiter**" aus.

9. Geben Sie auf der Seite **"Kennwort"** das Kennwort für die E-Mail-Adresse für das SIP-Gerät ein, und wählen Sie dann **"Anmelden"** aus.

10. Wählen Sie auf der Seite "**Versuchen Sie, sich bei Teams SIP-Geräte-Gateway anzumelden**" die Option **"Weiter"** aus.

## <a name="how-to-sign-in-and-sign-out"></a>So melden Sie sich an und abmelden

Nur die lokale Anmeldung wird für die persönlichen Geräte der Benutzer unterstützt. Führen Sie die folgenden Schritte aus, um ein Gerät vom Admin Center abzumelden:

1. Melden Sie sich beim [**Teams Admin Center**](https://admin.teams.microsoft.com) an.

2. Wählen Sie **Teams** **GeräteSIP-Geräte** >  aus.

3. Wählen Sie rechts ein SIP-Gerät und dann **"Abmelden" aus**.


### <a name="user-pairing-and-sign-in"></a>Benutzerkopplung und -anmeldung

Um ein SIP-Gerät zu koppeln, nachdem sich der Benutzer mit unternehmenseigenen Anmeldeinformationen authentifiziert hat, muss ein Benutzer Folgendes ausführen:

1. Drücken Sie die Anmeldung auf dem **SIP-Telefon** , um die Authentifizierungs-URL und den Kopplungscode anzuzeigen. Der Kopplungscode ist zeitabhängig. Wenn es abläuft, muss der Benutzer auf dem Telefon **zurück** drücken und den Anmeldevorgang erneut starten.

2. Navigieren Sie im Desktop- oder mobilen Browser des Benutzers zur Authentifizierungs-URL, und melden Sie sich mit den Unternehmensanmeldeinformationen an.

3. Geben Sie den auf dem SIP-Telefon angezeigten Kopplungscode in die Webauthentifizierungs-App ein, um das SIP-Telefon mit dem Konto des Benutzers zu koppeln. Bei einer erfolgreichen Anmeldung, die eine Weile dauern kann, zeigt das SIP-Telefon die Telefonnummer und den Benutzernamen an, wenn das Gerät dies unterstützt.

> [!NOTE]
> Der Speicherort des Geräts, das in der Azure Active Directory Webauthentifizierungs-App angezeigt wird, ist das SIP-Gateway-Rechenzentrum, mit dem das Gerät verbunden ist. SIP-Telefone im Bereich sind nicht OAuth-fähig, daher authentifiziert das SIP-Gateway den Benutzer über die Webauthentifizierungs-App und verbindet das Gerät dann mit den Anmeldeinformationen des Benutzers. Weitere Informationen finden Sie hier: [Microsoft Identity Platform und den OAuth 2.0-Geräteautorisierungs-Genehmigungsfluss](/azure/active-directory/develop/v2-oauth2-device-code).

### <a name="sign-out"></a>Abmelden

Um sich abzumelden, kann ein Gerätebenutzer folgende Aufgaben ausführen:

- Drücken Sie "Abmelden" auf dem **SIP-Gerät** , und führen Sie die auf dem Gerät beschriebenen Schritte aus. 

So melden Sie sich im Teams Admin Center von einem Gerät ab:

1. Melden Sie sich beim [**Teams Admin Center**](https://admin.teams.microsoft.com) an.

2. Wählen Sie **Teams** **GeräteSIP-Geräte** >  aus.

3. Wählen Sie rechts im **Bereich "SIP-Geräte** " das Gerät aus.

4. Wählen Sie im **Detailbereich** des Geräts die Registerkarte " **Details** " und oben rechts im Menü **"Aktionen** " die Option **"Abmelden" aus**. 

## <a name="view-and-monitor-sip-devices"></a>Anzeigen und Überwachen von SIP-Geräten

Sie können Ihren SIP-Gerätebestand im Teams Admin Center anzeigen und überwachen, nachdem sich die Benutzer der Geräte mindestens einmal angemeldet haben. Dazu gehen Sie so vor:

1. Melden Sie sich beim [Teams Admin Center](https://admin.teams.microsoft.com/) an.

2. Wählen Sie **Teams** **GeräteSIP-Geräte** >  aus. Alle angemeldeten SIP-Geräte sind auf der rechten Seite aufgeführt.

## <a name="restart-a-sip-device"></a>Neustarten eines SIP-Geräts

1. Melden Sie sich beim [Teams Admin Center](https://admin.teams.microsoft.com) an.

2. Wählen Sie **Teams** **GeräteSIP-Geräte** >  aus. 

3. Wählen Sie auf der rechten Seite das SIP-Gerät aus, das Sie neu starten möchten, und wählen Sie dann **"Neu starten"** aus.


> [!NOTE]
> - Das Entfernen eines SIP-Geräts aus Ihrem Mandanten ist derzeit im Teams Admin Center nicht verfügbar. 
> - Die Befehlsausführung hängt von der Geräteverfügbarkeit ab und entspricht möglicherweise nicht dem Ausführungsstatus, der im Teams Admin Center angezeigt wird. Wenn Sie versuchen, das SIP-Gateway auf einem Gerät zu aktivieren, das es nicht unterstützt, wird der Befehl nicht ausgeführt.

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>Synchronisierungsrichtlinienänderungen an SIP-Geräten zum Erzwingen von Richtlinien

Benutzerdetails und Richtlinien werden auf SIP-Geräte abgerufen, wenn sich Benutzer anmelden. Alle anschließenden Richtlinienänderungen für angemeldete Benutzer werden innerhalb einer Stunde mit dem Gerät synchronisiert. Geräte müssen ihre Registrierung regelmäßig mit dem SIP-Gateway aktualisieren lassen. SIP-Telefone sind von der Anrufumleitung abhängig, daher muss der Administrator das `AllowCallRedirect` Attribut `Set-CsTeamsCallingPolicy` auf `Enabled`festlegen.


## <a name="set-a-sip-devices-ui-language"></a>Festlegen der Benutzeroberflächensprache eines SIP-Geräts

Ein SIP-Gerät kann in der Regel Informationen in vielen Sprachen anzeigen. Das Festlegen der Benutzeroberflächensprache wirkt sich auf die Benutzeroberfläche aus, einschließlich Softkeys und Anmelde-/Abmeldesystemnachrichten. Das Festlegen der Benutzeroberflächensprache erfolgt auf dem Bereitstellungsserver, mithilfe des DHCP-Servers oder manuell durch Anfügen einer Codezeichenfolge an die URL wie in den folgenden Beispielen.

So legen Sie Deutsch für Polycom-, AudioCodes- und Yealink-Telefone fest:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

So legen Sie Japanisch für Cisco-Telefone fest:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_ja/$PSN.xml` 


### <a name="supported-languages"></a>Unterstützte Sprachen

|Sprachname|Sprachcode]
|-------------|-------------|
|Englisch (Standard)|De       |
|Spanisch      |es           |
|Japanisch     |ja           |
|Deutsch       |de           |
|Französisch       |Fr           |
|Portugiesisch   |Pt           |

> [!Note]
> - Japanisch wird nicht von Yealink und teilweise von Polycom VVX unterstützt.
> - Das System wird standardmäßig auf Englisch festgelegt, wenn die ausgewählte Sprache vom SIP-Endpunkt nicht unterstützt wird.
> - Wenn der **parameter lang_xx** nicht über die Bereitstellungs-URL festgelegt wird, wird Englisch als Standardsprache verwendet.
> - Wenn **die Anmeldung, um einen Notruf zu tätigen** , nicht in andere Sprachen übersetzt wird, wird bei der **Anmeldung** bei den folgenden IP-Telefonmodellen aufgrund von Bildschirmeinschränkungen eine abgekürzte Version nur in Englisch angezeigt:
>   - Poly VVX 150, VVX 201
>   - Cisco CP-6821, CP-7811, CP-7821, CP-7841, CP-7861
>   - Die Softkey-Bezeichnung für Voicemail ist aufgrund einer Einschränkung der Zeichenfolgenlänge in allen Sprachen für Poly VVX mit **VM-Text** hartcodiert.

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams und IPv6

DAS SIP-Gateway unterstützt nur IPv4. Microsoft Teams Dienst und Client unterstützen sowohl IPv4 als auch IPv6. Wenn Sie die Kommunikation mit Microsoft Teams steuern möchten, verwenden Sie die IP-Adressbereiche in [Microsoft 365 URLs und IP-Adressbereichen](/microsoft-365/enterprise/urls-and-ip-address-ranges).

## <a name="emergency-calling"></a>Notrufe

Das SIP-Gateway unterstützt nur statische Notfalladressen ( auch als registriert bezeichnet). Derzeit werden registrierte Adressen für Direct Routing-Szenarien nicht unterstützt. Weitere Informationen zu Notrufen finden Sie unter ["Planen und Verwalten von Notrufen](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)".

## <a name="report-problems-to-microsoft"></a>Melden von Problemen an Microsoft

Wenn Sie Probleme melden möchten, wenden Sie sich an [Microsoft-Support](https://support.microsoft.com).
