---
title: Bewährte Methoden für die Authentifizierung für Android-Geräte
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Ein Leitfaden zu bewährten Methoden für die Teams auf Android-Geräten.
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ffa30efd7f122b6d95c4545dd2d2517f3669472
ms.sourcegitcommit: 73d12d90fc20e3d943301f57ee434379d0b0e91b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2021
ms.locfileid: "61576165"
---
# <a name="authentication-best-practices-for-teams-android-devices"></a>Bewährte Methoden für die Authentifizierung Teams Android-Geräten

Dieser Artikel enthält allgemeine Anleitungen und bewährte Methoden für die Bereitstellung von Authentifizierungsrichtlinien für Teams und Anrufgeräte.

>[!NOTE]
>Für bedingten Zugriff ist ein Azure Active Directory (Azure AD) Premium erforderlich.

>[!NOTE]
>Richtlinien für mobile Android-Geräte gelten möglicherweise nicht für Teams Android-Geräte.


## <a name="personal-and-shared-devices"></a>Persönliche und freigegebene Geräte

Bei Teams Geräten, z. B. Besprechungsraumgeräten oder Telefonen in der Nähe, können nicht dieselben Anforderungen für Registrierung und Compliance verwendet werden, die normalerweise auf persönliche Geräte angewendet werden. Das Anwenden von Anforderungen für die persönliche Geräteauthentifizierung auf freigegebene Geräte hat folgende Anmeldeprobleme:

1.  **Geräte sind aufgrund von Kennwortrichtlinien ab-**

Konten, die auf Teams verwendet werden, verfügen über eine Kennwortablaufrichtlinie. Im Gegensatz zu Benutzern ist für die Konten, die mit gemeinsam genutzten Geräten verwendet werden, kein Anderer Benutzer zum Aktualisieren und Wiederherstellen des gültigen Zustands festgelegt, wenn ihre Kennwörter ablaufen. Wenn Kennwörter in Ihrer Organisation regelmäßig ablaufen und zurückgesetzt werden müssen, funktionieren diese Konten auf Teams-Geräten erst wieder, wenn ein Teams-Administrator das Kennwort zurückgesetzt und sich wieder angemeldet hat.

2.  **Geräte melden sich aufgrund von Richtlinien für bedingten Zugriff nicht an**

Freigegebene Geräte können nicht den Richtlinien Azure AD bedingten Zugriff für Benutzerkonten oder persönliche Geräte entsprechen. Wenn freigegebene Geräte mit Benutzerkonten oder persönlichen Geräten für eine Richtlinie für bedingten Zugriff gruppieren, kann es zu einem Fehler bei der Anmeldung kommen.

Wenn beispielsweise für den Zugriff auf ihre Daten mehrstufige Authentifizierung Teams, ist eine Benutzereingriff erforderlich, um die Authentifizierung abschließen zu können. Gemeinsam genutzte Geräte unterstützen die mehrstufige Authentifizierung nicht. Wenn das Konto so konfiguriert ist, dass es alle X Tage neu authentifiziert wird, kann ein gemeinsam genutztes Gerät die Herausforderung nicht ohne Eingreifen des Benutzers lösen.

## <a name="best-practices-for-teams-shared-device-deployments"></a>Bewährte Methoden für Teams Bereitstellung gemeinsam genutzter Geräte

Microsoft empfiehlt die folgenden Einstellungen, wenn Sie Teams in Ihrer Organisation bereitstellen.

### <a name="password-policy"></a>**Kennwortrichtlinie**

Teams gemeinsam genutzten Geräten sollten ein [Exchange-Ressourcenkonto verwenden.](/exchange/recipients-in-exchange-online/manage-resource-mailboxes) Diese Konten können entweder aus Active Directory synchronisiert oder direkt in Azure AD. Alle Kennwortablaufrichtlinien für Benutzer gelten auch für Konten, die auf gemeinsam genutzten Teams verwendet werden.

Um Unterbrechungen durch Kennwortablaufrichtlinien zu vermeiden, legen Sie die Kennwortablaufrichtlinie für freigegebene Geräte so ein, dass sie nie ablaufen.

Ab Teams-Geräten CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams Version 1449/1.0.94.2021022403 für Teams Phones) und [CY202 Update Nr. 2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams Version 1449/1.0.96.2021051904 für Microsoft Teams-Räume unter Android) können sich Mandantenadministratoren remote bei Teams-Geräten anmelden. Geben Sie keine Kennwörter für Techniker zum Einrichten von Geräten gemeinsam. Ein Administrator, verwenden Sie Die Remote-Anmeldung, um Überprüfungscodes aus, und melden Sie sich dann über das Admin Center Teams an.

Weitere Informationen finden Sie unter [Remotebereitstellung und Anmelden für Teams Android-Geräte.](/MicrosoftTeams/devices/remote-provision-remote-login) 

### <a name="conditional-access-policies"></a>**Richtlinien für bedingten Zugriff**

Azure AD bedingter Zugriff legt zusätzliche Anforderungen fest, die Geräte erfüllen müssen, um sich anmelden zu können. Lesen Teams für alle Geräte die folgenden Richtlinien, um zu ermitteln, ob Sie die entsprechenden Richtlinien verfasst haben. Eine Übersicht über bedingten Zugriff finden Sie unter [Was ist bedingter Zugriff?](/azure/active-directory/conditional-access/overview)

### <a name="multi-factor-authentication"></a>Mehrstufige Authentifizierung

Konten für gemeinsam genutzte Geräte sind mit einem Raum oder physischen Raum und nicht mit einem Benutzerkonto verknüpft. Da freigegebene Geräte die mehrstufige Authentifizierung nicht unterstützen, schließen Sie freigegebene Geräte aus allen Richtlinien für mehrstufige Authentifizierung aus.

>[!TIP]
>Verwenden Sie entweder [benannte Position, oder](/azure/active-directory/conditional-access/location-condition) [fordern Sie kompatible Geräte an,](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) um gemeinsam genutzte Geräte zu sichern.

### <a name="location-based-access-with-named-locations"></a>Standortbasierter Zugriff mit benannten Speicherorten

Wenn freigegebene Geräte an einem genau definierten Speicherort bereitgestellt werden, der mit einem [](/azure/active-directory/conditional-access/location-condition) Bereich von IP-Adressen identifiziert werden kann, können Sie bedingten Zugriff mit benannten Speicherorten für diese Geräte konfigurieren. Diese Bedingung erlaubt diesen Geräten den Zugriff auf Ihre Unternehmensressourcen nur, wenn sie sich innerhalb Ihres Netzwerks befinden.

### <a name="require-compliant-device"></a>Kompatibles Gerät erfordern

>[!NOTE]
>Für die Gerätekonformität ist eine Intune-Lizenz erforderlich.

Wenn Sie freigegebene Geräte bei Intune registrieren, können Sie die Gerätekonformität als Steuerelement im bedingten Zugriff konfigurieren, damit nur kompatible Geräte auf Ihre Unternehmensressourcen zugreifen können. Teams-Geräte können basierend auf der Gerätekonformität für Richtlinien für bedingten Zugriff konfiguriert werden. Weitere Informationen finden Sie unter [Bedingter Zugriff: Konformitäts- oder](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)Hybridzugriff Azure AD angeschlossenes Gerät.

Informationen zum Festlegen von Complianceeinstellungen für Ihre Geräte mit Intune finden Sie unter Verwenden von Compliancerichtlinien zum Festlegen von Regeln für Geräte, [die Sie mit Intune verwalten.](/intune/protect/device-compliance-get-started)

>[!NOTE]
> Freigegebene Geräte, die zum Hotdesking verwendet werden, sollten von den Compliancerichtlinien ausgeschlossen werden. Compliancerichtlinien verhindern, dass sich die Geräte beim Hot Desk-Benutzerkonto registrieren. Verwenden Sie stattdessen benannte Speicherorte, um diese Geräte zu schützen.
> Zur Erhöhung der Sicherheit können Sie [zusätzlich](/azure/active-directory/authentication/tutorial-enable-azure-mfa) zu den Richtlinien für benannte Speicherorte auch die mehrstufige Authentifizierung für Benutzer mit Hot-King-Benutzern erfordern.

### <a name="sign-in-frequency"></a>Anmeldehäufigkeit

Unter Bedingter Zugriff [](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) können Sie die Anmeldehäufigkeit so konfigurieren, dass Benutzer sich erneut anmelden müssen, um nach einem bestimmten Zeitraum auf eine Ressource zu zugreifen. Wenn bei Raumkonten die Anmeldehäufigkeit erzwungen wird, melden sich die gemeinsam genutzten Geräte ab, bis sie von einem Administrator erneut angemeldet werden. Microsoft empfiehlt, freigegebene Geräte aus den Richtlinien für Anmeldehäufigkeit zu ausschließen.

### <a name="filters-for-devices"></a>Filter für Geräte

[Der Filter für Geräte](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) ist ein Feature des bedingten Zugriffs, mit dem Sie genauere Richtlinien für Geräte basierend auf den in ihrer App verfügbaren Geräteeigenschaften Azure AD. Sie können auch ihre eigenen benutzerdefinierten Werte verwenden, indem Sie Erweiterungsattribute 1 bis 15 für das Geräteobjekt festlegen und diese dann verwenden.

Verwenden Sie Filter für Geräte, um Ihre gemeinsamen Geräte zu identifizieren und Richtlinien in zwei wichtigen Szenarien zu aktivieren:

1.  Ausschließen von geteilten Geräten aus Richtlinien, die für persönliche Geräte angewendet werden. Beispielsweise wird das Erfordern der Gerätekonformität nicht für gemeinsam genutzte Geräte erzwungen, die für Hot-King verwendet werden, sondern wird für alle anderen Geräte basierend auf der Modellnummer erzwungen.

2.  Erzwingen von speziellen Richtlinien für gemeinsam genutzte Geräte, die nicht auf persönliche Geräte angewendet werden sollen. Beispielsweise, wenn benannte Speicherorte als Richtlinie nur für allgemeine Geräte erforderlich sind, basierend auf einem Erweiterungsattribut, das Sie für diese Geräte festlegen (z. B.: "CommonAreaPhone").

>[!NOTE] 
> Einige Attribute wie **Modell,** **Hersteller** und **operatingSystemVersion** können nur festgelegt werden, wenn Geräte von Intune verwaltet werden. Wenn Ihre Geräte nicht von Intune verwaltet werden, verwenden Sie Erweiterungsattribute.