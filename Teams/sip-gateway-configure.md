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
ms.openlocfilehash: 1af44c5e3962f89346cae166bf40efa6a8622338
ms.sourcegitcommit: eddc03f777ce78bd5273708da9b1ab609ee20099
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/18/2022
ms.locfileid: "62065181"
---
# <a name="configure-sip-gateway"></a>Konfigurieren des SIP-Gateways

In diesem Artikel wird erläutert, wie Sie das SIP-Gateway so konfigurieren, dass Ihre Organisation kompatible SIP-Geräte mit Microsoft Teams. Informationen zu den für Ihre Organisation erforderlichen Hardware-, Software- und Lizenzen für das SIP-Gateway finden Sie unter Planen [des SIP-Gateways.](sip-gateway-plan.md)

Bevor Sie das SIP-Gateway konfigurieren können, gehen Sie wie folgt vor:

- **Setzen Sie SIP-Geräte auf die Werkseinstellungen zurück.** Die Benutzer Ihrer Organisation müssen jedes sip-Gerät, das mit dem SIP-Gateway verwendet wird, auf die Werkseinstellungen zurücksetzen. Anweisungen dazu finden Sie in den Anweisungen des Herstellers.

- **Öffnen Sie Ihre Firewall, um Microsoft 365 und Teams.** Öffnen Sie die Firewall Ihres Netzwerks, um Microsoft 365 und Teams zu senden, wie in den Office 365 URLs und [IP-Adressbereichen beschrieben.](/microsoft-365/enterprise/urls-and-ip-address-ranges)

- **Stellen Sie sicher, dass sich die SIP-Geräte nicht hinter einem Proxy befinden.** Stellen Sie sicher, dass http/s-Datenverkehr jeden http/s-Proxy des Unternehmens umgeht.

- **Öffnen Sie den UDP-Port.** Öffnen Sie den UDP-Port im Bereich 49152 bis 53247 für die IP-Bereiche 52.112.0.0/14 bis 52.120.0.0/14.

- **Öffnen Sie den TCP-Port.** Öffnen Sie TCP-Port 5061 für IP-Bereiche 52.112.0.0/14 bis 52.120.0.0/14.

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

- [Vergewissern Sie sich, dass das SIP-Gateway für Ihre Organisation verfügbar ist.](#verify-that-sip-gateway-is-available-for-your-organization)

- [Aktivieren Sie das SIP-Gateway für die Benutzer in Ihrer Organisation.](#enable-sip-gateway-for-the-users-in-your-organization)

- [Legen Sie die SERVER-URL für die Bereitstellungsserver des SIP-Gateways dar.](#set-the-sip-gateway-provisioning-server-url)

In diesem Artikel wird außerdem beschrieben, wie Sie:

- [Registrieren Sie SIP-Geräte entweder einzeln oder zur Vereinfachung in Batches.](#provision-and-enroll-sip-devices-as-common-area-phones)  


- [Zeigen Sie Ihre SIP-Geräte an, und überwachen Sie sie.](#view-and-monitor-sip-devices)

- [Aktivieren sie die Unterstützung für eine mehrsprachige Benutzeroberfläche.](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>Überprüfen, ob das SIP-Gateway für Ihre Organisation verfügbar ist

1. Melden Sie sich beim [Teams Admin Center an.](https://admin-teams.microsoft.com/)

2. Wählen Sie auf der linken **Seite Teams aus,** und sehen Sie, ob die Registerkarte **SIP-Geräte** angezeigt wird. In diesem Falls ist der SIP-Gatewaydienst für Ihre Organisation aktiviert.

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>Aktivieren des SIP-Gateways für die Benutzer in Ihrer Organisation

Sie können SIP Gateway für Ihre Organisation auf eine von zwei Arten aktivieren: mithilfe des Teams Admin Centers oder mithilfe eines PowerShell-Cmdlets.

### <a name="by-using-teams-admin-center"></a>Verwenden des Teams Admin Centers

Führen Sie die folgenden Schritte aus, Teams SIP-Gateway im Admin Center zu aktivieren:

1. Wechseln Sie zum [Teams Admin Center.](https://admin.teams.microsoft.com/)

2. Wählen Sie links unter **Sprache** die Option **Anrufrichtlinien aus.**

3. Wählen Sie rechts unter **Richtlinien** verwalten die geeignete Anrufrichtlinie aus, die den Benutzern zugewiesen ist, oder erstellen Sie bei Bedarf eine neue Anrufrichtlinie, und weisen Sie sie den erforderlichen Benutzern zu.

4. Wählen **Sie Richtlinien verwalten**, anschließend eine Richtlinie und dann Bearbeiten **aus.**

5. Aktivieren Sie die Einstellung für **SIP-Geräte, die für Anrufe verwendet werden können,** und wählen Sie dann **Speichern aus.**


### <a name="by-using-powershell"></a>Mithilfe von PowerShell

Sie können das SIP-Gateway auch mithilfe des [PowerShell-Set-CsTeamsCallingPolicy-Cmdlets](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) aktivieren. Um Benutzer für SIP-Geräte zu aktivieren, wählen Sie eine Richtlinie aus, und legen Sie das `-AllowSIPDevicesCalling` -Attribut auf `True` festgelegt. Der Standardwert ist , damit Benutzer ihre SIP-Geräte nur verwenden `False` können, wenn Sie sie aktivieren.


> [!NOTE]
> - Die Richtlinienverteilung kann bis zu 24 Stunden dauern.

## <a name="set-the-sip-gateway-provisioning-server-url"></a>Festlegen der URL des SIP-Gatewaybereitstellungsservers

Sie können die URL des SIP-Gatewaybereitstellungsservers in Ihrem DHCP-Server (Dynamic Host Configuration Protocol) festlegen. Benutzer, die remote arbeiten, müssen sie manuell konfigurieren.

### <a name="using-dhcp"></a>Verwenden von DHCP

Legen Sie für jedes SIP-Gerät eine der folgenden SIP-Gatewaybereitstellungsserver-URLs ein: 

- EMEA: `http://emea.ipp.sdg.teams.microsoft.com`
- Amerika: `http://noam.ipp.sdg.teams.microsoft.com`
- APAC: `http://apac.ipp.sdg.teams.microsoft.com`

Fügen Sie SIP-Geräte zu Ihrer Teams hinzu, indem Sie die oben aufgeführte SIP-Gatewaybereitstellungsserver-URL in Ihrem DHCP-Server konfigurieren. Weitere Informationen zum DHCP-Server finden Sie unter [Bereitstellen und Verwalten von DHCP.](/learn/modules/deploy-manage-dynamic-host-configuration-protocol) Außerdem können Sie DHCP-Option 42 verwenden, um den NTP-Server (Network Time Protocol) anzugeben, und DHCP-Option 2, um den Offset von UTC (Coordinated Universal Time) in Sekunden anzugeben. Die Geräte in Ihrer Organisation werden an den SIP-Gatewaybereitstellungsserver geroutet. Erfolgreich bereitgestellte SIP-Telefone zeigen das Teams und eine weiche Schaltfläche für die Anmeldung an.

Stellen Sie sicher, dass für SIP-Geräte die mindestens unterstützte Firmwareversion für onboarding verwendet wird. Während des Onboardings über das SIP-Gateway wird die Standardkonfigurations- und Authentifizierungs-Benutzeroberfläche an das Gerät übertragen. Informationen zur erforderlichen Firmwareversion für SIP-Geräte finden Sie unter [Planen für das SIP-Gateway.](sip-gateway-plan.md)

### <a name="manually"></a>Manuell

Benutzer, die remote arbeiten, müssen die Bereitstellungsserver-URL manuell in ihrem SIP-Gerät konfigurieren, indem sie die folgenden Schritte ausführen:

1. Öffnen **Einstellungen** auf dem Gerät, und erhalten Sie die IP-Adresse des Geräts.

2. Öffnen Sie ein Browserfenster, geben Sie die IP-Adresse des Geräts ein, melden Sie sich gegebenenfalls an, und konfigurieren Sie die URL des Bereitstellungsservers im Webdienstprogramm des Geräts.

3. Geben **Einstellungen** unter erweiterte **Einstellungen für** das Web-Hilfsprogramm die oben gezeigte BEREITSTELLUNGsserver-URL ein.

> [!NOTE]
> - Nur kompatible SIP-Geräte können in das SIP-Gateway onboarded werden. 
> - Cisco IP-Telefone müssen auf Multiplatform-Firmware blinken, bevor sie onboarded werden können. Informationen dazu finden Sie unter [Cisco Firmware-Konvertierungshandbuch.](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)
> - Verwenden Sie für Yealink-Telefone Option 66.
> - Verwenden Sie für Cisco,Poly- und AudioCode-Telefone Option 160. 
> - Für Cisco-Geräte fügen Sie **/$PSN.xml** an die URL des Bereitstellungsservers an.


## <a name="configure-conditional-access"></a>Konfigurieren des bedingten Zugriffs

Der bedingte Zugriff ist ein Azure Active Directory (Azure AD), mit dem sichergestellt wird, dass Geräte, die auf Ihre Microsoft 365-Ressourcen zugreifen, ordnungsgemäß verwaltet und sicher sind. SIP Gateway authentifiziert SIP-Geräte bei Azure AD. Wenn Ihre Organisation bedingten Zugriff für Geräte im Unternehmensnetzwerk verwendet, sollten die folgenden IP-Adressen ausgeschlossen werden:

- Nordamerika:
    - USA, Osten: 52.170.38.140
    - USA, Westen: 40.112.144.212
-   EMEA-Region:
    - Europa, Norden: 40.112.71.149
    - USA, Westen: 40.113.112.67
-   Region APAC:
    - Australien, Osten: 20.92.120.71
    - Australien, Südosten: 13.73.115.90

Weitere Informationen finden Sie unter [IP-Adressbereiche.](/azure/active-directory/conditional-access/location-condition#ip-address-ranges)


## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>Bereitstellen und Registrieren von SIP-Geräten als Telefone in der Nähe
> [!NOTE]
> Ein SIP-Gerät muss am SIP-Gateway installiert sein, bevor es registriert werden kann.

Um Ihre Aufgaben zu optimieren, können Sie SIP-Geräte im Teams Admin Center entweder zu einem bestimmten Zeitpunkt oder in Batches registrieren. Dazu gehen Sie so vor:

1. Melden Sie sich beim [**Teams Admin Center an.**](https://admin.teams.microsoft.com)

2. Wählen Sie **Teams**  >  **SIP-Geräte aus.**

3. Wählen Sie oben rechts Geräte **für** Aktionen bereitstellen aus,  >   und führen Sie einen der folgenden Schritte aus:

  - **So bereitstellungen Sie ein Gerät:**

     a. Wählen Sie **unter Aktivierung aus wartend** die Option **Hinzufügen aus.**

     b. Geben Sie **im Bereich MAC-Adressen**  hinzufügen die **MAC-Adresse** und den Standort des Geräts ein, und wählen Sie dann **Übernehmen aus.**
     
     c. Wählen **Sie unter Beim Aktivieren warten** das gerade hinzugefügte Gerät aus, und wählen Sie dann **Überprüfungscode generieren aus.**
     
     d. Notieren Sie **sich im Bereich** Geräte bereitstellen unter **Prüfcode** den Prüfcode für das SIP-Gerät.

   - **So können Sie viele Geräte bereitstellen:**

     a. Wählen **Sie rechts unter Warten** auf die Aktivierung die Option **Exportieren** aus (das Microsoft Excel Symbol).
     
     b. Wählen Sie **im Bereich Geräte** bereitstellen unter Hochladen **MAC-Adressen** die Option Vorlage **herunterladen aus.**
     
     c. Speichern **Template_Provisioning.csv** auf Ihrem Computer, und füllen Sie die **Felder MAC-ID** und **Speicherort** aus.
    
     d. Wählen Sie **im Bereich Geräte** bereitstellen die Option Hochladen **MAC-Adressen aus.** 

     e. Wählen Sie rechts im bereich **Hochladen Mac-Adressen** die Option Datei auswählen **aus,** und wählen Sie dann dieTemplate_Provisioning.csv **aus,** die Ihre Daten enthält.

     f. Wählen Sie **im Bereich** Geräte bereitstellen unter Bei Aktivierung  warten ein Gerät aus, und wählen Sie dann Überprüfungscode generieren aus, um für jedes bereitgestellte Gerät einen einmalverifizierungscode zu generieren.  Notieren Sie sich den Prüfcode für jedes SIP-Gerät.

4. Wählen Sie auf dem SIP-Gerät den Registrierungsfunktionscode gefolgt vom Prüfcode. Wählen Sie auf dem SIP-Gerät den Registrierungsfunktionscode 55* (wird vom SIP-Gateway für die Überprüfung des Codes zur einmalüberprüfung verwendet), gefolgt vom Prüfcode, der im Teams Admin Center für dieses bestimmte Gerät generiert \* wird. Wenn der Prüfcode beispielsweise als Prüfcode 123456, wählen Sie \* 55 \* 123456, um das Gerät zu registrieren.

5.  Wählen Sie **im Bereich Geräte** bereitstellen unter Auf Anmeldung **warten** die Option **Abmelden aus.**

6. Kopieren oder **notieren** Sie sich im Dialogfeld Benutzer anmelden den Kopplungscode des SIP-Geräts.

7. Wechseln Sie zu , geben Sie unter Code eingeben den Kopplungscode des SIP-Geräts ein, und [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) wählen Sie dann Weiter **aus.** 

8. Geben Sie auf **der Microsoft-Anmeldeseite** im Feld E-Mail oder Telefon die E-Mail-Adresse für das SIP-Gerät ein, und wählen Sie dann **Weiter aus.** 

9. Geben Sie **auf der** Seite Kennwort das Kennwort für die E-Mail-Adresse für das SIP-Gerät ein, und wählen Sie **anmelden aus.**

10. Wählen Sie auf der Seite Are **you trying to sign in to Teams SIP devices gateway** die Option Continue **aus.**

## <a name="how-to-sign-in-and-sign-out"></a>Anmelden und Abmelden

Für die persönlichen Geräte der Benutzer wird nur die lokale Anmeldung unterstützt. Führen Sie die folgenden Schritte aus, um sich über das Admin Center von einem Gerät abmelden:

1. Melden Sie sich beim [**Teams Admin Center an.**](https://admin.teams.microsoft.com)

2. Wählen Sie   >  **Teams-Geräte SIP-Geräte aus.**

3. Wählen Sie rechts ein SIP-Gerät und dann **Abmelden aus.**


### <a name="user-pairing-and-sign-in"></a>Benutzerkopplung und -anmeldung

Um ein SIP-Gerät zu koppeln, nachdem sich der Benutzer mit Unternehmensanmeldeinformationen authentifiziert hat, muss ein Benutzer:

1. Drücken **Sie auf dem SIP-Telefon** die Anmeldung, um die Authentifizierungs-URL und den Kopplungscode ein- und aus- koppeln zu können. Der Kopplungscode ist zeitempfindlich. Wenn es abläuft, muss der Benutzer auf dem Telefon auf **"Zurück"** klicken und den Anmeldevorgang erneut starten.

2. Navigieren Sie im Desktop- oder mobilen Browser des Benutzers zur Authentifizierungs-URL, und melden Sie sich mit den Unternehmensanmeldeinformationen an.

3. Geben Sie den auf dem SIP-Telefon angezeigten Kopplungscode in die Webauthentifizierungs-App ein, um das SIP-Telefon mit dem Konto des Benutzers zu koppeln. Bei einer erfolgreichen Anmeldung, die eine Weile dauern kann, zeigt das SIP-Telefon die Telefonnummer und den Benutzernamen an, sofern das Gerät dies unterstützt.

> [!NOTE]
> Der Standort des Geräts, das in der Webauthentifizierungs-App Azure Active Directory wird, ist das SIP-Gateway-Rechenzentrum, mit dem das Gerät verbunden ist. SIP-Telefone im Bereich sind nicht OAuth-fähig, daher authentifiziert das SIP-Gateway den Benutzer über die Webauthentifizierungs-App und paart das Gerät dann mit den Anmeldeinformationen des Benutzers. Weitere Informationen finden Sie [hier: Microsoft Identity Platform und den Autorisierungserteilungsablauf für OAuth 2.0-Geräte.](/azure/active-directory/develop/v2-oauth2-device-code)

### <a name="sign-out"></a>Abmelden

Ein Gerätebenutzer kann sich abmelden:

- Drücken **Sie auf dem SIP-Gerät** die Abmelde-Taste, und führen Sie die auf dem Gerät beschriebenen Schritte aus. 

So melden Sie sich auf dem Teams Admin Center ab:

1. Melden Sie sich beim [**Teams Admin Center an.**](https://admin.teams.microsoft.com)

2. Wählen Sie   >  **Teams-Geräte SIP-Geräte aus.**

3. Wählen Sie rechts im **Bereich SIP-Geräte** das Gerät aus.

4. Wählen Sie im **Detailbereich** des Geräts die Registerkarte **Details** aus, und wählen Sie oben rechts im Menü Aktionen die Option **Abmelden aus.**  


## <a name="view-and-monitor-sip-devices"></a>Anzeigen und Überwachen von SIP-Geräten

Sie können Ihren SIP-Geräteinventar im Teams Admin Center anzeigen und überwachen, nachdem sich die Benutzer der Geräte mindestens einmal anmelden. Dazu gehen Sie so vor:

1. Melden Sie sich beim [Teams Admin Center an.](https://admin.teams.microsoft.com/)

2. Wählen Sie   >  **Teams-Geräte SIP-Geräte aus.** Auf der rechten Seite sind alle angemeldeten SIP-Geräte aufgeführt.

## <a name="restart-a-sip-device"></a>Neustarten eines SIP-Geräts

1. Melden Sie sich beim [Teams Admin Center an.](https://admin.teams.microsoft.com)

2. Wählen Sie   >  **Teams-Geräte SIP-Geräte aus.** 

3. Wählen Sie rechts das SIP-Gerät aus, das Sie neu starten möchten, und wählen Sie dann Neu **starten aus.**

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>Synchronisieren von Richtlinienänderungen auf SIP-Geräten, um Richtlinien zu erzwingen

Benutzerdetails und -richtlinien werden bei der Anmeldung der Benutzer auf SIP-Geräten abgerufen. Alle anschließenden Richtlinienänderungen für angemeldete Benutzer werden innerhalb einer Stunde mit dem Gerät synchronisiert. Auf Geräten muss ihre Registrierung regelmäßig mit dem SIP-Gateway aktualisiert werden. SIP-Telefone sind von der Anrufumleitung abhängig, daher muss der Administrator das `AllowCallRedirect` -Attribut in auf `Set-CsTeamsCallingPolicy` `Enabled` festlegen.


## <a name="set-a-sip-devices-ui-language"></a>Festlegen der Benutzeroberflächensprache eines SIP-Geräts

Auf einem SIP-Gerät können Informationen normalerweise in vielen Sprachen angezeigt werden. Das Festlegen der Ui-Sprache wirkt sich auf die Benutzeroberfläche aus, einschließlich Softkeys und An-/Abmeldesystemmeldungen. Das Festlegen der Benutzeroberflächensprache erfolgt auf dem Bereitstellungsserver, mit DHCP-Server oder manuell durch Anfügen einer Codezeichenfolge in der URL, wie in den folgenden Beispielen gezeigt.

So legen Sie Deutsch für Polycom-, AudioCodes- und Yealink-Telefone fest:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

So legen Sie Japanisch für Cisco Phones fest:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_ja/$PSN.xml` 


### <a name="supported-languages"></a>Unterstützte Sprachen

|Name der Sprache|Sprachcode]
|-------------|-------------|
|Englisch (Standard)|de       |
|Spanisch      |es           |
|Japanisch     |ja           |
|Deutsch       |de           |
|Französisch       |fr           |
|Portugiesisch   |pt           |

> [!Note]
> - Japanisch wird von Yealink nicht und teilweise von Polycom VVX unterstützt.
> - Das System wird standardmäßig auf Englisch festgelegt, wenn die ausgewählte Sprache vom SIP-Endpunkt nicht unterstützt wird.
> - Wenn der **lang_xx** nicht über die Bereitstellungs-URL festgelegt wird, wird Englisch als Standardsprache verwendet.
> - Wenn  der Text für die Anmeldung für einen Notruf nicht in andere Sprachen übersetzt wird, wird bei den folgenden IP-Telefonmodellen aufgrund bildschirmgrößer Einschränkungen nur eine abgekürzte Version in Englisch angezeigt: 
>   - Poly VVX 150, VVX 201
>   - Cisco CP-6821, CP-7811, CP-7821, CP-7841, CP-7861
>   - Voicemail-Softkey-Bezeichnungen werden aufgrund einer Einschränkung der Zeichenfolgenlänge in allen Sprachen für Poly VVX mit **VM-Text** hartcodiert.

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams und IPv6

SIP-Gateway unterstützt nur IPv4. Microsoft Teams-Dienst und -Client unterstützen IPv4 und IPv6. Wenn Sie die Kommunikation mit E-Mail-Microsoft Teams möchten, verwenden Sie die IP-Adressbereiche in Microsoft 365 [URLs und IP-Adressbereichen](/microsoft-365/enterprise/urls-and-ip-address-ranges).

## <a name="emergency-calling"></a>Notrufe

SIP Gateway unterstützt nur statische –auch als registrierte Notfalladressen bezeichnete Notfalladressen. Derzeit werden registrierte Adressen in Direct Routing-Szenarien nicht unterstützt. Weitere Informationen zu Notrufen finden Sie unter [Planen und Verwalten von Notrufen.](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)

## <a name="report-problems-to-microsoft"></a>Melden von Problemen an Microsoft

Um Probleme zu melden, wenden Sie sich [an den Microsoft-Support.](https://support.microsoft.com)
