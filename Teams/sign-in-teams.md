---
title: Anmelden bei Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: anwara
description: Hier erfahren Sie, wie die moderne Authentifizierung funktioniert, wie Sie zwischen Konten wechseln und wie Sie Probleme mit der modernen Authentifizierung behandeln. Es wird auch erläutert, wie man Microsoft Teams anweisen kann, das Vorausfüllen des Benutzernamens (UPN) bei der Anmeldung zu ignorieren.
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98502d623edda6117b2838d2bc71197a43baf394
ms.sourcegitcommit: 84d99b266dea2a972774d781b92eccc67d6c197a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197520"
---
<a name="sign-in-to-microsoft-teams"></a>Anmelden bei Microsoft Teams
==========================

## <a name="windows-users"></a>Windows-Benutzer

Microsoft empfiehlt Unternehmen, neuere Versionen von Windows 10 mit Hybrid Domain Join- oder Azure AD Join-Konfiguration zu verwenden. Durch die Nutzung aktueller Versionen wird sichergestellt, dass die Nutzerkonten im Windows-Webkonto-Manager vorbereitet werden, wodurch wiederum die einmalige Anmeldung bei Microsoft Teams und anderen Microsoft-Anwendungen ermöglicht wird. Single Sign-On bietet mehr Benutzerfreundlichkeit (automatische Anmeldung) und einen besseren Sicherheitsstatus.

Microsoft Teams verwendet moderne Authentifizierung, um die Anmeldung einfach und sicher zu gestalten. Um zu erfahren, wie sich Benutzer bei Teams anmelden, lesen Sie bitte [Anmelden in Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

### <a name="how-modern-authentication-works"></a>So funktioniert moderne Authentifizierung

Bei der modernen Authentifizierung handelt es sich um einen Prozess, der Microsoft Teams mitteilt, dass Benutzer ihre Anmeldeinformationen (wie Ihre geschäftliche E-Mail-Adresse und das Kennwort) bereits anderswo eingegeben haben, und dass sie diese nicht erneut eingeben müssen, um die App zu starten. Der Ablauf hängt von einigen Faktoren ab, beispielsweise ob Benutzer in Windows oder auf einem Mac arbeiten. Er hängt zudem davon ab, ob Ihre Organisation die einstufige oder die mehrstufige Authentifizierung aktiviert hat. Die mehrstufige Authentifizierung umfasst in der Regel die Überprüfung von Anmeldeinformationen über ein Telefon, die Bereitstellung eines eindeutigen Codes, das Eingeben einer PIN oder die Verwendung eines Fingerabdrucks. Hier ist eine Übersicht über jedes Szenario moderner Authentifizierung.

Die moderne Authentifizierung ist für alle Organisationen verfügbar, die Microsoft Teams verwenden. Wenn Benutzer den Prozess nicht abschließen können, liegt möglicherweise ein Problem mit der Azure AD-Konfiguration Ihrer Organisation vor. Weitere Informationen finden Sie unter [Wieso habe ich Probleme bei der Anmeldung bei Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)

- Wenn sich Nutzer bereits mit ihrem Arbeits- oder Schulkonto bei Windows oder anderen Office-Apps angemeldet haben, werden sie beim Starten von Teams direkt zur App weitergeleitet. Sie müssen ihre Anmeldeinformationen nicht eingeben.

- Microsoft empfiehlt die Verwendung von Windows 10 Version 1903 oder höher, um die beste Single Sign-On-Erfahrung zu erzielen.

- Wenn Benutzer an keiner anderen Stelle in ihrem Microsoft-Geschäfts-, Schul- oder Unikonto angemeldet sind, werden sie beim Starten von Microsoft Teams entweder zu einer einstufigen oder zu einer mehrstufigen Authentifizierung (SFA oder MFA) aufgefordert. Dieser Vorgang hängt davon ab, was Ihre Organisation für den Anmeldeprozess festgelegt hat.

- Wenn Benutzer bei einem domänengebundenen Computer angemeldet sind, werden sie beim Start von Teams möglicherweise aufgefordert, einen weiteren Authentifizierungsschritt durchzuführen, je nachdem, ob sich Ihre Organisation für MFA entschieden hat oder ob ihr Computer bereits MFA zum Anmelden erfordert. Wenn ihr Computer bereits MFA zur Anmeldung erfordert, startet die App automatisch, wenn  sie Teams öffnen.

- Auf PCs, die einer Domain zugehören, kann Teams den Anmeldebildschirm vorab mit dem Nutzerprinzipalnamen (UPN) füllen, wenn SSO nicht möglich ist. Es gibt Fälle, in denen Sie dies möglicherweise nicht möchten, insbesondere wenn Ihre Organisation verschiedene UPNs lokal und in Azure Active Directory verwendet. In diesem Fall können Sie den folgenden Windows-Registrierungsschlüssel verwenden, um die Vorbelegung des UPN zu deaktivieren:

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > Das Überspringen oder Ignorieren des Vorab-Ausfüllens von Benutzernamen ist für Benutzernamen, die in „.local“ oder „.corp“ enden, standardmäßig aktiviert, daher müssen Sie keinen Registrierungsschlüssel festlegen, um diese zu deaktivieren.

### <a name="signing-out-of-teams-after-completing-modern-authentication"></a>Abmeldung von Microsoft Teams nach Abschluss der modernen Authentifizierung

Benutzer können sich von Teams abmelden, indem sie über ihr Profilbild oben in der App **Abmelden** auswählen. Alternativ können sie mit der rechten Maustaste auf das App-Symbol in ihrer Taskleiste klicken und dann **Abmelden** wählen. Nach der Abmeldung von Teams müssen sie ihre Anmeldedaten erneut eingeben, um die App zu starten.

### <a name="signing-in-to-another-account-on-a-domain-joined-computer"></a>Anmelden mit einem anderen Konto auf einem PC, der einer Domäne beigetreten ist

Benutzer auf einem Computer, der einer Domäne beigetreten ist, können sich möglicherweise nicht bei Teams mit einem anderen Konto in der gleichen Active Directory-Domäne anmelden.

## <a name="macos-users"></a>macOS-Benutzer

Unter macOS werden die Benutzer von Microsoft Teams aufgefordert, ihren Benutzernamen und ihre Anmeldeinformationen einzugeben, und je nach den Einstellungen Ihres Unternehmens werden sie möglicherweise zur mehrstufigen Authentifizierung aufgefordert. Sobald die Benutzer ihre Anmeldeinformationen eingegeben haben, werden sie nicht mehr aufgefordert, sie erneut anzugeben. Von diesem Zeitpunkt an startet Teams automatisch, wenn sie am gleichen Computer arbeiten.

## <a name="teams-on-ios-and-android-users"></a>Microsoft Teams für iOS- und Android-Benutzer

Bei der Anmeldung sehen Benutzer von Mobilgeräten eine Liste aller Microsoft 365-Konten, bei denen sie entweder aktuell angemeldet sind oder zuvor auf ihrem Gerät angemeldet waren. Die Benutzer können auf eines der Konten tippen, um sich anzumelden. Es gibt zwei Szenarien für die Anmeldung auf Mobilgeräten:

1. Wenn der Benutzer aktuell über das ausgewählte Konto bei anderen Office 365- oder Microsoft 365-Apps angemeldet ist, wird er direkt zu Microsoft Teams geleitet. In diesem Fall muss er seine Anmeldeinformationen nicht eingeben.

2. Wenn der Benutzer nirgendwo sonst bei seinem Microsoft 365-Konto angemeldet ist, wird er, abhängig von den Vorgaben der Anmelderichtlinien Ihrer Organisation für Mobilgeräte, zu einer einstufigen bzw. mehrstufigen Authentifizierung (SFA oder MFA) aufgefordert.

> [!NOTE]
> Damit die Anmeldeerfahrung für Benutzer der Beschreibung in diesem Abschnitt entspricht, muss auf ihren Geräten Teams für iOS, Version 2.0.13 (Build 2020061704) oder höher, bzw. Teams für Android, Version 1416/1.0.0.2020061702 oder höher, ausgeführt werden.

## <a name="using-teams-with-multiple-accounts"></a>Verwenden von Teams mit mehreren Konten

Teams für IOS und Android unterstützt die parallele Verwendung mehrerer Geschäfts- oder Schulkonten sowie mehrerer persönlichen Konten. Teams-Desktopanwendungen unterstützen ab Dezember 2020 ein Geschäfts-/Schulkonto und ein persönliches Konto nebeneinander. Die Unterstützung für mehrere Geschäfts-/Schulkonten wird zu einem späteren Zeitpunkt folgen.

Die folgenden Bilder zeigen, wie Benutzer in Microsoft Teams-Anwendungen für Mobilgeräte mehrere Konten hinzufügen können.

:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="Hinzufügen mehrerer Konten in Microsoft Teams":::

## <a name="restrict-sign-in-to-teams"></a>Einschränken der Anmeldung bei Teams

Ein Unternehmen möchte möglicherweise einschränken, wie die vom Unternehmen genehmigte Apps auf verwalteten Geräten verwendet werden, um beispielsweise die Möglichkeit von Studenten oder Mitarbeitern einzuschränken, auf Daten von anderen Organisationen zuzugreifen oder die vom Unternehmen genehmigten Apps für persönliche Zwecke zu verwenden. Diese Einschränkungen können erzwungen werden, indem Geräterichtlinien festgelegt werden, die von Teams-Anwendungen erkannt werden.   

### <a name="how-to-restrict-sign-in-on-mobile-devices"></a>Einschränken der Anmeldung auf mobilen Geräten

Microsoft Teams für iOS und Android bietet IT-Administratoren die Möglichkeit, Kontokonfigurationen auf Microsoft 365-Konten zu übertragen. Das funktioniert mit jedem Mobile Device Management-Anbieter (MDM, Verwaltung mobiler Geräte), der den [Managed App Configuration](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html)-Kanal für iOS oder den [Android Enterprise](https://developer.android.com/work/managed-configurations)-Kanal für Android verwendet.

Sie können die Konfigurationseinstellungen über Intune im Azure-Portal bereitstellen, wenn Benutzer bei Microsoft Intune angemeldet sind.

Sobald die Kontoeinrichtungskonfiguration beim MDM-Anbieter festgelegt sind und nachdem der Benutzer das Gerät registriert hat, wird Microsoft Teams für iOS und Android auf der Teams-Anmeldeseite nur noch die erlaubten Konten anzeigen. Der Benutzer kann auf jedes der zulässigen Konten auf dieser Seite tippen, um sich anzumelden.

Legen Sie die folgenden Konfigurationsparameter im Azure Intune-Portal für verwaltete Geräte fest.

|Plattform |Key  |Wert  |
|---------|---------|---------|
|iOS     |  **IntuneMAMAllowedAccountsOnly**       | **Enabled**: Das einzige zulässige Konto ist das über den IntuneMAMUPN-Schlüssel definierte verwaltete Benutzerkonto.<br> **Disabled** (oder ein Wert, bei dem es sich nicht um eine groß-/ kleinschreibungsunabhängige Übereinstimmung mit **Enabled** handelt): Jedes Konto ist zulässig.        |
|iOS     |   **IntuneMAMUPN**      |   Der UPN des Kontos, das für die Anmeldung bei Microsoft Teams zulässig ist.<br> Bei in Intune registrierten Geräten kann das {{userprincipalname}}-Token zur Darstellung des registrierten Benutzerkontos verwendet werden.       |
|Android     |**com.microsoft.intune.mam.AllowedAccountUPNs**         |    Die einzigen zulässigen Konten sind die durch diesen Schlüssel definierten verwalteten Benutzerkonten.<br> Ein oder mehrere durch Semikolons [;] getrennte UPNs.<br> Bei in Intune registrierten Geräten kann das {{userprincipalname}}-Token zur Darstellung des registrierten Benutzerkontos verwendet werden.

Sobald die Konto Setup-Konfiguration festgelegt wurde, schränkt Microsoft Teams die Möglichkeit zur Anmeldung ein, sodass nur zulässigen Konten auf registrierten Geräten der Zugriff gewährt wird.

Wenn Sie eine App-Konfigurationsrichtlinie für verwaltete iOS-/iPadOS-Geräte erstellen möchten, lesen Sie [Hinzufügen von App-Konfigurationsrichtlinien für verwaltete iOS-/iPadOS-Geräte](/mem/intune/apps/app-configuration-policies-use-ios).

Wenn Sie eine App-Konfigurationsrichtlinie für verwaltete Android-Geräte erstellen möchten, lesen Sie [Hinzufügen von App-Konfigurationsrichtlinien für verwaltete Android-Geräte](/mem/intune/apps/app-configuration-policies-use-android).

### <a name="how-to-restrict-sign-in-on-desktop-devices"></a>Einschränken der Anmeldung auf Desktopgeräten
Teams-Apps unter Windows und MacOS erhalten Unterstützung für Geräterichtlinien, die das Anmelden bei Ihrer Organisation einschränken. Die Richtlinien können über herkömmliche Geräteverwaltungslösungen wie MDM (Mobile Device Management) oder GPO (Group Policy Object) festgelegt werden. 

Wenn diese Richtlinie auf einem Gerät konfiguriert ist, können sich die Benutzer nur mit Konten anmelden, die sich in einem Azure AD-Mandanten befinden, der in der „Mandanten-Zulassungsliste“ enthalten ist, welche in der Richtlinie definiert wurde. Die Richtlinie gilt für alle Anmeldungen, einschließlich des ersten und weiterer Konten. Wenn Ihre Organisation über mehrere Azure AD-Mandanten verfügt, können Sie in der Zulassungsliste mehrere Mandanten-IDs einschließen. Links zum Hinzufügen eines weiteren Kontos sind in der Teams-App möglicherweise weiterhin sichtbar, funktionieren aber nicht mehr.

> [!NOTE]
>1. Die Richtlinie schränkt nur Anmeldungen ein. Sie schränkt nicht die Möglichkeit ein, dass Benutzer als Gast in andere Azure AD-Mandanten eingeladen werden oder zu anderen Mandanten wechseln können.
>2. Die Richtlinie erfordert Teams für Windows Version 1.3.00.30866 oder höher, und Teams für MacOS Version 1.3.00.30882 (Veröffentlichung Mitte November 2020).

**Richtlinien für Windows** Administrative Vorlagendateien (ADMX/ADML) stehen im [Download Center](https://www.microsoft.com/download/details.aspx?id=49030) zur Verfügung (der beschreibende Name der Richtlinieneinstellung in der administrativen Vorlagendatei ist „Anmeldung in Teams auf Konten in bestimmten Mandanten beschränken“). Zusätzlich können Sie Schlüssel in der Windows-Registrierung manuell festlegen:

- Wertname: RestrictTeamsSignInToAccountsFromTenantList
- Werttyp: String
- Wertdaten: Mandanten-ID oder eine durch Kommas getrennte Liste der Mandanten-IDs
- Pfad: Benutzen Sie einen der folgenden Pfade

 Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Cloud\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\16.0\Teams

Beispiel: SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = Mandanten-ID oder SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = Mandanten-ID1, Mandanten-ID2, Mandanten-ID3

**Richtlinien für MacOS** Verwenden Sie für von MacOS verwaltete Geräte .plist, um Anmeldebeschränkungen bereitzustellen. Das Konfigurationsprofil ist eine .plist-Datei, die aus mit einem Schlüssel identifizierten Einträgen besteht (der Schlüssel bezeichnet den Namen der Einstellung), gefolgt von einem Wert, der von der Art der Einstellung abhängt. Werte können entweder einfach sein (z. B. ein numerischer Wert) oder komplex, z. B. eine geschachtelte Liste von Einstellungen.

- Domäne: com.microsoft.teams
- Schlüssel: RestrictTeamsSignInToAccountsFromTenantList
- Datentyp: String
- Kommentare: Geben Sie eine durch Kommas getrennte Liste der Mandanten-IDs der Azure AD ein.


## <a name="sign-out-on-mobile-devices"></a>Abmelden auf mobilen Geräten

Benutzer von Mobilgeräten können sich von Microsoft Teams abmelden, indem sie zum Menü wechseln, das Menü **Mehr** und dann **Abmelden** auswählen. Nach der Abmeldung müssen die Benutzer ihre Anmeldeinformationen beim nächsten Starten der App erneut eingeben.

> [!NOTE]
> Microsoft Teams für Android verwendet die einmalige Anmeldung (SSO, Single Sign-On), um die Anmeldung zu vereinfachen. Die Benutzer sollten sicherstellen, dass Sie sich neben Microsoft Teams von **allen** Microsoft-Apps abmelden, um sich vollständig von der Android-Plattform abmelden zu können.

### <a name="global-sign-in-and-sign-out"></a>Globales Anmelden und Abmelden

Die Teams-Android-App unterstützt jetzt das globale Anmelden und Abmelden, um Mitarbeitern in Service und Produktion einen einfachen Anmelde- und Abmeldevorgang zu bieten. Ein Mitarbeiter kann ein Gerät aus dem Pool geteilter Geräte auswählen und es für die Dauer seiner Schicht mittels einmaliger Anmeldung zu "seinem" machen. Am Ende der Schicht sollte er sich global von dem Gerät abmelden können. Dadurch werden alle seine persönlichen Informationen und Unternehmensinformationen von dem Gerät entfernt, damit er es wieder zurück in den Gerätepool geben kann. Um diese Funktion nutzen zu können, muss sich das Gerät im Modus "Freigegeben" befinden. Wenn Sie erfahren möchten, wie ein freigegebenes Gerät eingerichtet wird, lesen Sie [Verwenden eines "Freigegeben"-Gerätemodus in Android](/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode).

Der Anmeldevorgang ähnelt der standardmäßigen Anmeldung bei Microsoft Teams, während die Abmeldung wie in den folgenden beiden Bildern dargestellt abläuft:

![das Mobiltelefon mit dargestellter Abmeldung](media/global-SignOut.png)  

## <a name="urls-and-ip-address-ranges"></a>URLs und IP-Adressbereiche

Microsoft Teams setzt eine Internetverbindung voraus. Informationen zu Endpunkten, die für Kunden mit Microsoft Teams in Office 365-Plänen, Behörden und andere Clouds erreichbar sein sollten, finden Sie unter [URLs und IP-Adressbereiche für Office 365](/office365/enterprise/urls-and-ip-address-ranges).

> [!IMPORTANT]
> Microsoft Teams benötigt derzeit Zugriff (TCP-Port 443) auf den Google ssl.gstatic.com-Dienst für alle Benutzer. Dies gilt selbst dann, wenn Sie Gstatic nicht verwenden. Diese Anforderung wird demnächst (erste Hälfte 2020) aus Microsoft Teams entfernt. Dieser Artikel wird dann entsprechend aktualisiert.

## <a name="related-topics"></a>Verwandte Themen

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)