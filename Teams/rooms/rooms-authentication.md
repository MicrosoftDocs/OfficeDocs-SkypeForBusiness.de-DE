---
title: Authentifizierung in Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie die moderne Authentifizierung für Microsoft Teams Rooms konfigurieren.
ms.openlocfilehash: 93577c74005c8ad266739da0991f31e384a57ba6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117483"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Authentifizierung in Microsoft Teams Rooms

Die Kontoverwaltung für Microsoft Teams Rooms-Geräte wird auf Anwendungsebene behandelt. Die Anwendung stellt eine Verbindung mit Microsoft Teams, Skype for Business und Exchange ein, um Ressourcen für das Raumkonto zu erhalten, um Anruf- und Besprechungserfahrungen zu ermöglichen. Das Gerät wird kontoagnostisch aufbewahrt, um immer eins zu ermöglichen, Anrufszenarien (für Geräte, die mit einem Anrufplan konfiguriert sind) und benutzerdefinierte Sperrmechanismen, die auf diesen Geräten implementiert sind. Dies bedeutet, dass die Authentifizierung für diese Geräte auf andere Weise als für Endbenutzergeräte geschieht.  

Die moderne Authentifizierung wird für alle Kunden empfohlen, die Microsoft Teams Rooms-Geräte mit Microsoft 365 oder Office 365 verwenden. Wenn Sie über eine lokale Bereitstellung von Exchange-Server [](/office365/enterprise/hybrid-modern-auth-overview) oder Skype for Business-Server verfügen, konfigurieren Sie die moderne Hybridauthentifizierung mit Azure Active Directory (Azure AD), um die Verwendung der modernen Authentifizierung zu aktivieren.

Die moderne Authentifizierung wird in Microsoft Teams Rooms, Version 4.4.25.0 und höher, unterstützt.

## <a name="modern-authentication"></a>Moderne Authentifizierung

Wenn Sie die moderne Authentifizierung mit der Microsoft Teams Rooms-Anwendung verwenden, wird die Active Directory Authentication Library (ADAL) verwendet, um eine Verbindung mit Microsoft Teams, Exchange und Skype for Business herzustellen. Ein Microsoft Teams Rooms-Gerät ist ein freigegebenes Gerät und führt einen nächtlichen Neustart durch, um ein reibungsloses Funktionieren sicherzustellen und wichtige Betriebssystem-, Treiber-, Firmware- oder Anwendungsupdates zu erhalten. Der moderne Authentifizierungsmechanismus verwendet in OAuth 2.0 den [Autorisierungstyp](/azure/active-directory/develop/v2-oauth-ropc) für Kennwortanmeldeinformationen des Ressourcenbesitzers, für den kein Benutzereingriff erforderlich ist. Dies ist einer der wichtigsten Unterschiede zwischen der Funktionsweise der modernen Authentifizierung für Benutzerkonten und Ressourcenkonten, die von der Microsoft Teams Rooms-Anwendung verwendet werden. Daher sollten Microsoft Teams Rooms-Ressourcenkonten nicht für die Verwendung der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA), der Smartcardauthentifizierung oder der clientzertifikatbasierten Authentifizierung konfiguriert werden (die alle für Endbenutzer verfügbar sind).

Der andere wichtige Unterschied zwischen der Funktionsweise der modernen Authentifizierung auf Microsoft Teams Rooms-Geräten und Endbenutzergeräten besteht in der Nichtnutzung eines Ressourcenkontos zum Anwenden von Richtlinien für bedingten Zugriff auf Geräteebene in Azure Active Directory und Endpoint Manager, da Geräteinformationen bei Verwendung dieses Granttyps nicht übergeben werden. Stattdessen können Sie ein Gerät in Microsoft Endpoint Manager registrieren und Compliancerichtlinien anwenden, indem Sie die Anweisungen unter Verwalten von [Teams-Besprechungsräumen mit Intune verwenden.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Aktivieren der modernen Authentifizierung auf einem Microsoft Teams Rooms-Gerät

Damit Microsoft Teams Rooms die moderne Authentifizierung mit Skype for Business und Exchange verwenden kann, aktivieren Sie die clientseitige Einstellung für die moderne Authentifizierung auf dem Microsoft Teams Rooms-Gerät. Dies können Sie in den Geräteeinstellungen oder in der XML-Konfigurationsdatei tun.

> [!NOTE]
> Bevor Sie die clientseitige Einstellung für die moderne Authentifizierung aktivieren, stellen Sie sicher, dass Ihre Umgebung ordnungsgemäß für die Verwendung der modernen Authentifizierung eingerichtet ist.

### <a name="using-device-settings"></a>Verwenden von Geräteeinstellungen

1. Wechseln Sie auf dem Gerät Microsoft Team Rooms zu **Mehr** (**...**).
    
2. Wählen **Sie Einstellungen** aus, und geben Sie dann den Benutzernamen und das Kennwort des Geräteadministrators ein.
3. Wechseln Sie zur **Registerkarte Konto,** aktivieren Sie **moderne Authentifizierung,** und wählen Sie dann Speichern und **beenden aus.**

### <a name="using-the-xml-config-file"></a>Verwenden der XML-Konfigurationsdatei

Legen Sie in SkypeSettings.xml -Datei das moderne Authentifizierungs-XML-Element wie folgt **auf True** ein.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Informationen zum Anwenden der Einstellung finden Sie [unter Verwalten einer Microsoft Teams Rooms-Konsoleneinstellungen remote mit einer XML-Konfigurationsdatei.](xml-config-file.md)

## <a name="prepare-your-environment-for-modern-authentication"></a>Vorbereiten Ihrer Umgebung für die moderne Authentifizierung

Bevor Sie beginnen, stellen Sie sicher, dass Sie sich mit den Identitätsmodellen aus, die Sie mit Office 365 und Azure AD verwenden müssen. Weitere Informationen finden Sie unter [Office 365-Identitätsmodelle und Azure Active Directory](/Office365/Enterprise/about-office-365-identity) sowie unter Hybrididentität und Verzeichnissynchronisierung für Microsoft [365 oder Office 365.](/Office365/Enterprise/plan-for-directory-synchronization)

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Aktivieren der modernen Authentifizierung in Microsoft 365 oder Office 365

Informationen zum Aktivieren der modernen Authentifizierung für Exchange Online finden Sie unter [Aktivieren der modernen Authentifizierung in Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) Wenn Sie Skype for Business Online verwenden, sollten Sie auch sicherstellen, dass die moderne Authentifizierung für Skype for Business Online aktiviert ist. Weitere Informationen finden Sie unter [Skype for Business Online: Aktivieren Ihres Mandanten für die moderne Authentifizierung.](https://aka.ms/SkypeModernAuth)

Es wird empfohlen, grundlegende Authentifizierungsrichtlinien für Exchange Online nicht zu entfernen oder die grundlegende Authentifizierung für Ihren Mandanten zu deaktivieren, bis Sie überprüft haben, ob Microsoft Teams Rooms-Geräte sich erfolgreich mit Exchange Online, Teams und Skype for Business Online anmelden können.

Weitere Informationen zum Deaktivieren der einfachen Authentifizierung in Exchange Online finden Sie unter [Deaktivieren der Standardauthentifizierung in Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)

## <a name="hybrid-modern-authentication"></a>Moderne Hybridauthentifizierung

Um eine erfolgreiche Authentifizierung für Ihren lokalen Exchange-Server und/oder Skype for Business-Server sicherzustellen, müssen Sie sicherstellen, dass das ressourcenkonto, das mit Microsoft Teams Rooms verwendet wird, für die Autorisierung von Azure AD konfiguriert ist. 

Die Authentifizierungsflüsse von Teams Rooms variieren je nach Authentifizierungskonfiguration. Für Kunden, die eine verwaltete Domäne verwenden, verwendet Teams Rooms [OAuth 2.0 Resource Owner Password Credentials](/azure/active-directory/develop/v2-oauth-ropc) with Azure Active Directory. Für Kunden, die eine Verbunddomäne verwenden, wird [jedoch OAuth 2.0 SAML Bearer Assertion Flow](/azure/active-directory/develop/v2-saml-bearer-assertion) verwendet.

> [!NOTE]
> Ihr Identitätsanbieter benötigt möglicherweise bestimmte Konfigurationen oder Einstellungen für die Integration in Azure Active Directory oder Office 365. Wenden Sie sich an Ihren Identitätsanbieter, wenn Sie Hilfe beim Konfigurieren der Authentifizierung mit Teams Rooms benötigen.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Für Microsoft Teams Rooms spezifische Voraussetzungen

Die Voraussetzungen für die Aktivierung der modernen Authentifizierung in Ihrer Hybridtopologie finden Sie unter Übersicht über die moderne Hybridauthentifizierung und die Voraussetzungen für die Verwendung mit lokalen Skype for Business- und [Exchange-Servern.](/office365/enterprise/hybrid-modern-auth-overview) Alle im Artikel erläuterten Voraussetzungen gelten.

Da Microsoft Teams Rooms jedoch die Kennwortanmeldeinformationen des [Ressourcenbesitzers](https://tools.ietf.org/html/rfc6749#section-1.3.3) und die zugrunde liegenden REST-APIs für die moderne Authentifizierung verwendet, sind die folgenden wichtigen Unterschiede zu beachten, die für Microsoft Teams Rooms spezifisch sind.

- Sie müssen über Exchange Server 2016 CU8 oder höher oder Exchange Server 2019 CU1 oder höher verfügen.
- Sie müssen über Skype for Business Server 2015 CU5 oder höher oder Skype for Business Server 2019 oder höher verfügen.
- MFA wird unabhängig von ihrer Topologie nicht unterstützt.
- In Microsoft Teams Rooms werden sip- und UPN-konflikte nicht unterstützt. Sie müssen ein Microsoft Teams Rooms-Konto mit demselben UPN und SIP erstellen, damit es funktioniert.
- Wenn Sie einen drittanbieter-Authentifizierungsanbieter verwenden, der von Azure AD unterstützt wird, muss er einen aktiven Authentifizierungsfluss über WS-Trust unterstützen.
- Verwenden Sie keine Richtlinien für bedingten Zugriff auf Geräteebene für ein Ressourcenkonto, das mit der Anwendung konfiguriert ist. Dies führt zu Anmeldefehlern. Registrieren Sie stattdessen ein Gerät in Microsoft Intune, und wenden Sie Compliancerichtlinien anhand der unter Verwalten von [Teams-Besprechungsräumen mit Intune veröffentlichten Richtlinien an.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

### <a name="configure-exchange-server"></a>Konfigurieren Exchange Server

Informationen zum Aktivieren der modernen Hybridauthentifizierung in Exchange Server finden Sie unter Konfigurieren von lokalen Exchange Server für die Verwendung der [modernen Hybridauthentifizierung.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="configure-skype-for-business-server"></a>Konfigurieren von Skype for Business Server

Informationen zum Aktivieren der modernen Hybridauthentifizierung mit Skype for Business Server finden Sie unter Konfigurieren der lokalen Skype for Business-Authentifizierung für die Verwendung [der modernen Hybridauthentifizierung.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Entfernen oder Deaktivieren von Skype for Business und Exchange

Wenn Ihr Setup keine moderne Hybridauthentifizierung zu lässt oder Sie die moderne Hybridauthentifizierung für Exchange oder Skype for Business entfernen oder deaktivieren müssen, lesen Sie Entfernen oder Deaktivieren der modernen Hybridauthentifizierung aus Skype for Business und [Exchange.](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)

### <a name="azure-ad-conditional-access"></a>Bedingter Azure AD-Zugriff

Sie können ein Ressourcenkonto konfigurieren, das mit Microsoft Teams Rooms für DEN IP-/standortbasierten Zugriff verwendet wird. Weitere Informationen finden Sie unter [Bedingter Zugriff: Blockieren des Zugriffs nach Speicherort](/azure/active-directory/conditional-access/howto-conditional-access-policy-location).

Es werden keine anderen Richtlinien für den bedingten Zugriff unterstützt. Weitere Informationen zur Gerätekonformität finden Sie unter [Verwalten von Teams-Besprechungsräumen mit Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)