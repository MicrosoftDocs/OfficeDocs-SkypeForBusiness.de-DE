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
description: Erfahren Sie, wie Sie die moderne Authentifizierung für Microsoft Teams-Räume konfigurieren.
ms.openlocfilehash: 5667b4bc2ab356ff9776282a6142a22abd33caa1
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760877"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Authentifizierung in Microsoft Teams-Räume

Die Kontoverwaltung für Microsoft Teams-Räume wird auf Anwendungsebene behandelt. Die Anwendung stellt eine Verbindung mit Microsoft Teams, Skype for Business und Exchange her, um Ressourcen für das Ressourcenkonto abzurufen, um Anruf- und Besprechungserfahrungen zu ermöglichen. Teams-Räume verwendet ein dediziertes Ressourcenkonto, um Always-On-Funktionen, Anrufszenarien (für Geräte, die mit einem Anrufplan konfiguriert sind) und benutzerdefinierte Sperrmodusmechanismen zu ermöglichen. Dies bedeutet, dass die Authentifizierung für Teams-Räume auf eine andere Weise erfolgt als für Endbenutzergeräte.  

Die moderne Authentifizierung wird für alle Kunden empfohlen, die Microsoft Teams-Räume mit Microsoft 365 oder Office 365 verwenden. Wenn Sie über eine lokale Bereitstellung von Exchange Server oder Skype for Business Server verfügen, konfigurieren Sie die [moderne Hybridauthentifizierung](/office365/enterprise/hybrid-modern-auth-overview) mit Azure Active Directory (Azure AD), um die Verwendung der modernen Authentifizierung zu aktivieren.

Die moderne Authentifizierung wird unter Microsoft Teams-Räume Version 4.4.25.0 und höher unterstützt.

## <a name="modern-authentication"></a>Moderne Authentifizierung

Wenn Sie die moderne Authentifizierung mit der Microsoft Teams-Räume-Anwendung verwenden, wird die Active Directory-Authentifizierungsbibliothek (ADAL) verwendet, um eine Verbindung mit Microsoft Teams, Exchange und Skype for Business herzustellen. Der moderne Authentifizierungsmechanismus verwendet den Autorisierungsgenehmigungstyp für [Kennwortanmeldeinformationen des Ressourcenbesitzers](/azure/active-directory/develop/v2-oauth-ropc) in OAuth 2.0, der keinen Benutzereingriff erfordert. Dies ist einer der wichtigsten Unterschiede zwischen der Funktionsweise der modernen Authentifizierung für Benutzerkonten und Ressourcenkonten, die von Microsoft Teams-Räume verwendet werden. Aus diesem Grund sollten Microsoft Teams-Räume Ressourcenkonten nicht für die Verwendung der mehrstufigen Authentifizierung (MFA), smartcardauthentifizierung oder clientzertifikatbasierter Authentifizierung (alle für Endbenutzer verfügbar) konfiguriert werden.

Der andere wichtige Unterschied zwischen der Funktionsweise der modernen Authentifizierung auf Microsoft Teams-Räume- und Endbenutzergeräten besteht darin, dass Sie kein Ressourcenkonto verwenden können, um Richtlinien für bedingten Zugriff auf Geräteebene in Azure Active Directory und Endpoint Manager anzuwenden, da Geräteinformationen bei Verwendung dieses Gewährungstyps nicht übergeben werden. Stattdessen können Sie ein Gerät in Microsoft Endpoint Manager registrieren und Compliancerichtlinien anwenden. Weitere Informationen finden Sie unter [Bedingter Zugriff und Intune Compliance für Microsoft Teams-Räume](conditional-access-and-compliance-for-devices.md).

## <a name="enable-modern-authentication-on-microsoft-teams-rooms"></a>Aktivieren der modernen Authentifizierung auf Microsoft Teams-Räume

Damit Microsoft Teams-Räume die moderne Authentifizierung mit Skype for Business und Exchange verwenden können, aktivieren Sie die clientseitige Einstellung für die moderne Authentifizierung auf Microsoft Teams-Räume. Sie können dies in den Geräteeinstellungen oder in der XML-Konfigurationsdatei tun.

> [!NOTE]
> Bevor Sie die clientseitige Einstellung für die moderne Authentifizierung aktivieren, stellen Sie sicher, dass Ihre Umgebung ordnungsgemäß für die Verwendung der modernen Authentifizierung eingerichtet ist.

### <a name="using-device-settings"></a>Verwenden von Geräteeinstellungen

1. Wechseln Sie auf Microsoft Teams-Räume zu **Mehr** (**...**).
    
2. Wählen Sie **Einstellungen** aus, und geben Sie dann den Benutzernamen und das Kennwort des Geräteadministrators ein.
3. Wechseln Sie zur Registerkarte **"Konto** ", aktivieren Sie die **moderne Authentifizierung**, und wählen Sie dann **"Speichern" und "Beenden" aus**.

### <a name="using-the-xml-config-file"></a>Verwenden der XML-Konfigurationsdatei

Legen Sie in Ihrer SkypeSettings.xml-Datei das XML-Element für die moderne Authentifizierung wie folgt auf **"True"** fest.

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Informationen zum Anwenden der Einstellung finden [Sie unter Verwalten einer Microsoft Teams-Räume Konsoleneinstellungen remote mit einer XML-Konfigurationsdatei](xml-config-file.md).

## <a name="prepare-your-environment-for-modern-authentication"></a>Vorbereiten Ihrer Umgebung für die moderne Authentifizierung

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Identitätsmodelle verstehen, die mit Office 365 und Azure AD verwendet werden sollen. Weitere Informationen finden Sie unter [Office 365 Identitätsmodelle und Azure Active Directory](/Office365/Enterprise/about-office-365-identity) sowie bei [der Hybrididentitäts- und Verzeichnissynchronisierung für Microsoft 365 oder Office 365](/Office365/Enterprise/plan-for-directory-synchronization).

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Aktivieren der modernen Authentifizierung in Microsoft 365 oder Office 365

Informationen zum Aktivieren der modernen Authentifizierung für Exchange Online finden [Sie unter Aktivieren der modernen Authentifizierung in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

Es wird empfohlen, die Standardauthentifizierungsrichtlinien für Exchange Online zu entfernen oder die Standardauthentifizierung für Ihren Mandanten zu deaktivieren, bis Sie überprüft haben, dass sich Microsoft Teams-Räume Geräte erfolgreich mit Exchange Online und Teams anmelden können.

Weitere Informationen zum Deaktivieren der Standardauthentifizierung in Exchange Online finden [Sie unter Deaktivieren der Standardauthentifizierung in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).

## <a name="hybrid-modern-authentication"></a>Moderne Hybridauthentifizierung

Um eine erfolgreiche Authentifizierung bei Ihrem lokalen Exchange Server und/oder Skype for Business Server sicherzustellen, müssen Sie sicherstellen, dass das mit Microsoft Teams-Räume verwendete Ressourcenkonto so konfiguriert ist, dass die Autorisierung von Azure AD abgerufen wird.

Teams-Räume Authentifizierungsabläufe variieren je nach Authentifizierungskonfiguration. Für Kunden, die eine verwaltete Domäne verwenden, verwendet Teams-Räume [die OAuth 2.0-Ressourcenbesitzer-Kennwortanmeldeinformationen](/azure/active-directory/develop/v2-oauth-ropc) mit Azure Active Directory. Für Kunden, die eine Verbunddomäne verwenden, wird jedoch [OAuth 2.0 SAML Bearer Assertion Flow](/azure/active-directory/develop/v2-saml-bearer-assertion) verwendet.

> [!NOTE]
> Ihr Identitätsanbieter benötigt möglicherweise bestimmte Konfigurationen oder Einstellungen für die Integration in Azure Active Directory oder Office 365. Wenden Sie sich an Ihren Identitätsanbieter, wenn Sie Hilfe beim Konfigurieren der Authentifizierung mit Teams-Räume benötigen.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Spezifische Voraussetzungen für Microsoft Teams-Räume

Die Voraussetzungen für die Aktivierung der modernen Authentifizierung in Ihrer Hybridtopologie werden in der [Übersicht über die moderne Hybridauthentifizierung und den Voraussetzungen für die Verwendung mit lokalen Skype for Business und Exchange Servern](/office365/enterprise/hybrid-modern-auth-overview) behandelt. Es gelten alle im Artikel erläuterten Voraussetzungen.

Da Microsoft Teams-Räume jedoch die Autorisierung von [Kennwortanmeldeinformationen für den Ressourcenbesitzer](https://tools.ietf.org/html/rfc6749#section-1.3.3) und die zugrunde liegenden REST-APIs für die moderne Authentifizierung verwendet, sind die folgenden wichtigen Unterschiede zu beachten, die für Microsoft Teams-Räume spezifisch sind.

- Sie müssen über Exchange Server 2016 CU8 oder höher oder Exchange Server 2019 CU1 oder höher verfügen.
- Sie müssen über Skype for Business Server 2015 CU5 oder höher oder Skype for Business Server 2019 oder höher verfügen.
- MFA wird unabhängig von der vorhandenen Topologie nicht unterstützt.
- Microsoft Teams-Räume unterstützt keine SIP- und UPN-Nichtübereinstimmung. Sie müssen ein Microsoft Teams-Räume Konto mit dem gleichen UPN und SIP erstellen, damit es funktioniert.
- Wenn Sie einen drittanbieterbasierten Authentifizierungsanbieter verwenden, der von Azure AD unterstützt wird, muss dieser einen aktiven Authentifizierungsfluss über WS-Trust unterstützen.
- Verwenden Sie keine Richtlinien für bedingten Zugriff auf Geräteebene für ein mit der Anwendung konfiguriertes Ressourcenkonto. Dies führt zu Anmeldefehlern. Registrieren Sie stattdessen ein Gerät in Microsoft Intune und wenden Sie Compliancerichtlinien an. Weitere Informationen finden Sie unter [Bedingter Zugriff und Intune Compliance für Microsoft Teams-Räume](conditional-access-and-compliance-for-devices.md).

### <a name="configure-exchange-server"></a>Konfigurieren von Exchange Server

Informationen zum Aktivieren der modernen Hybridauthentifizierung in Exchange Server finden Sie unter [Konfigurieren Exchange Server lokalen Authentifizierung für die Verwendung der modernen Hybridauthentifizierung](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="configure-skype-for-business-server"></a>Konfigurieren von Skype for Business Server

Informationen zum Aktivieren der modernen Hybridauthentifizierung mit Skype for Business Server finden Sie unter [Konfigurieren Skype for Business lokalen Authentifizierung für die Verwendung der modernen Hybridauthentifizierung](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Entfernen oder Deaktivieren von Skype for Business und Exchange

Wenn Ihr Setup keine moderne Hybridauthentifizierung zulässt oder Sie die moderne Hybridauthentifizierung für Exchange oder Skype for Business entfernen oder deaktivieren müssen, lesen Sie [das Entfernen oder Deaktivieren der modernen Hybridauthentifizierung aus Skype for Business und Exchange](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).

### <a name="azure-ad-conditional-access"></a>Bedingter Azure AD-Zugriff

Sie können ein Ressourcenkonto konfigurieren, das mit Microsoft Teams-Räume für DEN IP-/standortbasierten Zugriff verwendet wird. Weitere Informationen finden Sie [unter Bedingter Zugriff: Zugriff nach Speicherort blockieren](/azure/active-directory/conditional-access/howto-conditional-access-policy-location).

Es werden keine anderen Richtlinien für bedingten Zugriff unterstützt. Weitere Informationen zur Gerätecompliance finden Sie unter ["Unterstützter bedingter Zugriff" und Intune Compliancerichtlinien für Microsoft Teams-Räume](supported-ca-and-compliance-policies.md).
