---
title: Authentifizierung in Microsoft Teams-Räume
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie die moderne Authentifizierung für Microsoft Teams-Räume
ms.openlocfilehash: d38bf63e0ed1dc9e5cb52445fab88e617fda6169
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015195"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Authentifizierung in Microsoft Teams-Räume

Die Kontoverwaltung für Microsoft Teams-Räume wird auf Anwendungsebene behandelt. Die Anwendung stellt eine Verbindung zu Microsoft Teams, Skype for Business Und Exchange, um Ressourcen für das Ressourcenkonto zu erhalten, um Anruf- und Besprechungserfahrungen zu ermöglichen. Teams-Räume verwendet ein dediziertes Ressourcenkonto, um immer-on-Funktionen, Aufrufszenarien (für Geräte, die mit einem Aufrufplan konfiguriert sind) und benutzerdefinierte Sperrmechanismen zu ermöglichen. Dies bedeutet, dass Teams-Räume Authentifizierung auf andere Weise als bei Endbenutzergeräten geschieht.  

Moderne Authentifizierung wird allen Kunden empfohlen, die Microsoft Teams-Räume mit Microsoft 365 oder Office 365. Wenn Sie über eine lokale Bereitstellung von Exchange-Server oder Skype for Business-Server verfügen, konfigurieren Sie die hybride moderne Authentifizierung mit Azure Active Directory (Azure AD), um die Verwendung der modernen Authentifizierung zu aktivieren. [](/office365/enterprise/hybrid-modern-auth-overview)

Die moderne Authentifizierung wird Microsoft Teams-Räume Version 4.4.25.0 und höher unterstützt.

## <a name="modern-authentication"></a>Moderne Authentifizierung

Wenn Sie die moderne Authentifizierung mit der Microsoft Teams-Räume-Anwendung verwenden, wird Active Directory Authentication Library (ADAL) verwendet, um eine Verbindung mit Microsoft Teams, Exchange und Skype for Business. Der moderne Authentifizierungsmechanismus verwendet in OAuth 2.0 den [Autorisierungs-Autorisierungstyp](/azure/active-directory/develop/v2-oauth-ropc) für die Kennwortberechtigung des Ressourcenbesitzers, für den keine Benutzereingriffe erforderlich sind. Dies ist einer der Hauptunterschiede zwischen der Funktionsweise der modernen Authentifizierung für Benutzerkonten und Ressourcenkonten, die von Microsoft Teams-Räume. Daher sollten Microsoft Teams-Räume-Ressourcenkonten nicht für die Verwendung der mehrstufigen Authentifizierung( Multi-Factor Authentication, MFA), der Smartcard-Authentifizierung oder der auf Clientzertifikaten basierenden Authentifizierung konfiguriert werden(die alle für Endbenutzer verfügbar sind).

Der andere wichtige Unterschied zwischen der Funktionsweise der modernen Authentifizierung auf Microsoft Teams-Räume- und Endbenutzergeräten besteht im: Sie können in Azure Active Directory und Endpoint Manager keine Richtlinien für bedingten Zugriff auf Geräteebene mithilfe eines Ressourcenkontos anwenden, da bei Verwendung dieses Zugriffstyps keine Geräteinformationen übergeben werden. Stattdessen können Sie ein Gerät in Microsoft Endpoint Manager registrieren und Compliancerichtlinien anwenden, indem Sie die Anleitung unter Verwalten von Besprechungsräumen [Teams Intune verwenden.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

## <a name="enable-modern-authentication-on-microsoft-teams-rooms"></a>Aktivieren der modernen Authentifizierung bei Microsoft Teams-Räume

Wenn Microsoft Teams-Räume moderne Authentifizierung mit Skype for Business und Exchange verwenden möchten, aktivieren Sie die clientseitige Einstellung für die moderne Authentifizierung auf Microsoft Teams-Räume. Dies können Sie in den Geräteeinstellungen oder in der XML-Konfigurationsdatei tun.

> [!NOTE]
> Bevor Sie die clientseitige Einstellung für die moderne Authentifizierung aktivieren, stellen Sie sicher, dass Ihre Umgebung ordnungsgemäß für die Verwendung der modernen Authentifizierung eingerichtet ist.

### <a name="using-device-settings"></a>Verwenden von Geräteeinstellungen

1. Wechseln Microsoft Teams-Räume zu **Mehr** (**...**).
    
2. Wählen **Einstellungen** aus, und geben Sie dann den Benutzernamen und das Kennwort für den Geräteadministrator ein.
3. Wechseln Sie zur **Registerkarte Konto,** aktivieren Sie **moderne Authentifizierung,** und wählen Sie **dann Speichern und beenden .**

### <a name="using-the-xml-config-file"></a>Verwenden der XML-Konfigurationsdatei

Legen Sie SkypeSettings.xml XML-Element für die moderne Authentifizierung wie folgt auf True (wahr) in **Ihrer** Datei SkypeSettings.xml.

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Informationen zum Anwenden der Einstellung finden Sie unter Verwalten Microsoft Teams-Räume [Einer Konsoleneinstellungen remote mit einer XML-Konfigurationsdatei.](xml-config-file.md)

## <a name="prepare-your-environment-for-modern-authentication"></a>Vorbereiten der Umgebung für die moderne Authentifizierung

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Identitätsmodelle kennen, die für die Verwendung mit Office 365 und Azure AD. Weitere Informationen finden Sie unter [Office 365 identitätsmodellen](/Office365/Enterprise/about-office-365-identity) und Azure Active Directory hybride Identität und Verzeichnissynchronisierung für Microsoft 365 [oder Office 365.](/Office365/Enterprise/plan-for-directory-synchronization)

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Aktivieren der modernen Authentifizierung in Microsoft 365 oder Office 365

Informationen zum Aktivieren der modernen Authentifizierung für Exchange Online Sie unter Aktivieren der modernen [Authentifizierung in Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)

Es wird empfohlen, die Standardauthentifizierungsrichtlinien für Exchange Online zu entfernen oder die Standardauthentifizierung für ihren Mandanten erst zu deaktivieren, wenn Sie überprüft haben, dass Microsoft Teams-Räume-Geräte sich erfolgreich mit Exchange Online und Teams.

Weitere Informationen zum Deaktivieren der Standardauthentifizierung in Exchange Online finden Sie unter Deaktivieren der [Standardauthentifizierung in Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)

## <a name="hybrid-modern-authentication"></a>Moderne Hybridauthentifizierung

Um eine erfolgreiche Authentifizierung bei Ihrem lokalen Exchange-Server und/oder Skype for Business-Server sicherzustellen, müssen Sie sicherstellen, dass das Ressourcenkonto, das mit Microsoft Teams-Räume verwendet wird, für das Erhalten von Autorisierung von Azure AD.

Teams-Räume Authentifizierungsflüsse variieren je nach Authentifizierungskonfiguration. Für Kunden, die eine verwaltete Domäne verwenden, verwendet Teams-Räume Kennwort für [OAuth 2.0-Ressourcenbesitzer-Kennwortinformationen](/azure/active-directory/develop/v2-oauth-ropc) Azure Active Directory. Für Kunden, die eine Verbunddomäne verwenden, wird [jedoch OAuth 2.0 SAML Bearer Assertion Flow](/azure/active-directory/develop/v2-saml-bearer-assertion) verwendet.

> [!NOTE]
> Ihr Identitätsanbieter benötigt möglicherweise bestimmte Konfigurationen oder Einstellungen für die Integration Azure Active Directory oder Office 365. Wenden Sie sich an Ihren Identitätsanbieter, wenn Sie Hilfe beim Konfigurieren der Authentifizierung mit Teams-Räume.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Voraussetzungen für Microsoft Teams-Räume

Die Voraussetzungen für die Aktivierung der modernen Authentifizierung in Ihrer Hybridtopologie werden unter Übersicht über die moderne Hybridauthentifizierung und die Voraussetzungen für die Verwendung mit lokalen Skype for Business- und [Exchange-Servern behandelt.](/office365/enterprise/hybrid-modern-auth-overview) Es gelten alle Voraussetzungen, die in diesem Artikel erläutert werden.

Da Microsoft Teams-Räume jedoch die Kennwortautorisierung des [Ressourcenbesitzers](https://tools.ietf.org/html/rfc6749#section-1.3.3) und die zugrunde liegenden REST-APIs für die moderne Authentifizierung verwendet, sind die folgenden wichtigen Unterschiede zu beachten, die speziell für die moderne Authentifizierung Microsoft Teams-Räume.

- Sie müssen über Exchange Server 2016 CU8 oder höher verfügen oder Exchange Server 2019 CU1 oder höher.
- Sie müssen über Skype for Business Server 2015 CU5 oder höher oder Skype for Business Server 2019 oder höher verfügen.
- MFA wird unabhängig von Ihrer Topologie nicht unterstützt.
- Microsoft Teams-Räume sip- und UPN-Konflikte werden von Microsoft Teams-Räume nicht unterstützt. Sie müssen ein Microsoft Teams-Räume-Konto mit demselben UPN und SIP erstellen, damit es funktioniert.
- Wenn Sie einen Drittanbieter-Authentifizierungsanbieter verwenden, der von Azure AD unterstützt wird, muss er einen aktiven Authentifizierungsablauf über WS-Trust unterstützen.
- Verwenden Sie keine Richtlinien für bedingten Zugriff auf Geräteebene für ein Ressourcenkonto, das mit der Anwendung konfiguriert ist. Dies führt zu Fehlern bei der Anmeldung. Registrieren Sie stattdessen ein Gerät in ihrem Microsoft Intune und wenden Sie Compliancerichtlinien anhand der unter Verwalten von Teams [mit Intune veröffentlichten Richtlinien an.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

### <a name="configure-exchange-server"></a>Konfigurieren Exchange Server

Informationen zum Aktivieren der modernen Hybridauthentifizierung in Exchange Server finden Sie unter Konfigurieren Exchange Server lokalen Authentifizierung für die Verwendung [der modernen Hybridauthentifizierung.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="configure-skype-for-business-server"></a>Konfigurieren Skype for Business Server

Informationen zum Aktivieren der modernen Hybridauthentifizierung Skype for Business Server Sie unter Konfigurieren von Skype for Business lokalen Authentifizierung für die Verwendung der modernen [Hybridauthentifizierung.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Entfernen oder Deaktivieren von Skype for Business und Exchange

Wenn Ihre Einrichtung die hybride moderne Authentifizierung nicht zu lässt oder Sie die hybride moderne Authentifizierung für Exchange oder Skype for Business entfernen oder deaktivieren müssen, lesen Sie Entfernen oder Deaktivieren der modernen Hybridauthentifizierung von Skype for Business und [Exchange.](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)

### <a name="azure-ad-conditional-access"></a>Azure AD bedingten Zugriff

Sie können ein ressourcenbasiertes Konto konfigurieren, das Microsoft Teams-Räume für IP-/standortbasierter Zugriff verwendet wird. Weitere Informationen finden Sie unter [Bedingter Zugriff: Zugriff nach Speicherort blockieren.](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)

Es werden keine anderen Richtlinien für bedingten Zugriff unterstützt. Weitere Informationen zur Gerätekonformität finden Sie [unter Verwalten Teams von Besprechungsräumen mit Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)
