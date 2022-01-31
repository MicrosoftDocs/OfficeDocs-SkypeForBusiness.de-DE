---
title: Bewährte Methoden für die Authentifizierung Microsoft Teams Verwaltung gemeinsam genutzter Geräte von Android-Geräten.
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Bewährte Methoden für die Verwaltung gemeinsam genutzter Android-Teams. Dies umfasst Bedingungszugriff, Kennwortrichtlinie, Ratschläge zur mehrstufigen Authentifizierung und vieles mehr.
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
ms.openlocfilehash: 070c662c09d8b8159dbce850501026f67dabb203
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279233"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>Bewährte Methoden für die Authentifizierung Teams Verwaltung gemeinsam genutzter Geräte auf Android-Geräten

Die Ziele der mit der Entwicklung verwendeten Teams machen unterschiedliche Geräteverwaltungsstrategien erforderlich. Beispielsweise hat ein von einer Vertriebsmitarbeiter verwendetes persönliches Geschäfts-Tablet andere Anforderungen als ein Telefon, das von vielen Kundendienstmitarbeitern gemeinsam genutzt wird.

Sicherheitsadministratoren und Betriebsteams müssen die Geräte planen, die in der Organisation verwendet werden können. Sie müssen *Sicherheitsmaßnahmen implementieren,* die für jeden Zweck am besten geeignet sind. Die Empfehlungen in diesem Artikel erleichtern einige dieser Entscheidungen.

>[!NOTE]
>Für bedingten Zugriff ist ein Azure Active Directory (Azure AD) Premium erforderlich.

>[!NOTE]
>Richtlinien für mobile Android-Geräte gelten möglicherweise nicht für Teams Android-Geräte.

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>Authentifizierungsempfehlungen unterscheiden sich bei persönlichen und gemeinsam genutzten Android-Geräten

Freigegebene Teams können nicht dieselben Registrierungs- und Complianceanforderungen erfüllen, die auf persönlichen Geräten verwendet werden. Das Anwenden von Anforderungen für die persönliche Geräteauthentifizierung auf gemeinsam genutzte Geräte verursacht Anmeldeprobleme.

1.  **Geräte werden aufgrund von Kennwortrichtlinien ab signiert.**

Konten, die auf Teams verwendet werden, verfügen über eine Kennwortablaufrichtlinie. Die Konten, die mit gemeinsam genutzten Geräten verwendet werden, verfügen nicht über einen bestimmten Benutzer, der das Kennwort aktualisieren und in einem funktionierenden Zustand wiederherstellen kann. Wenn in Ihrer Organisation Kennwörter gelegentlich ablaufen und zurückgesetzt werden müssen, funktionieren diese Konten auf Teams-Geräten erst wieder, wenn ein Teams-Administrator das Kennwort zurückgesetzt und sich wieder angemeldet hat.

**Herausforderung**: Wenn es um den Zugriff geht. Teams von einem Gerät aus verfügt das Konto einer Person über eine Kennwortablaufrichtlinie. Wenn das Kennwort abläuft, wird es einfach geändert. Konten, die auf gemeinsam *genutzten Geräten* verwendet werden (Ressourcenkonten), sind jedoch möglicherweise nicht mit einer einzelnen Person verbunden, die ein Kennwort bei Bedarf ändern kann. Dies bedeutet, dass ein Kennwort ablaufen kann und die Mitarbeiter an Ort und Stelle sind und nicht wissen, wie sie ihre Arbeit fortsetzen können.

Wenn Ihre Organisation eine Kennwortzurücksetzung erfordert oder den Kennwortablauf erzwingt, stellen Sie sicher, dass ein Teams-Administrator bereit ist, das Kennwort zurückzusetzen, damit sich diese freigegebenen Konten wieder anmelden können.

2.  **Geräte melden sich aufgrund von Richtlinien für bedingten Zugriff nicht an.**

**Herausforderung**: Freigegebene Geräte können den Richtlinien für Azure AD bedingten Zugriff für Benutzerkonten oder persönliche Geräte nicht entsprechen. Wenn freigegebene Geräte mit Benutzerkonten oder persönlichen Geräten für eine Richtlinie für bedingten Zugriff gruppieren, kann es zu einem Fehler bei der Anmeldung *kommen*.

Wenn beispielsweise mehrstufige Authentifizierung für den Zugriff auf ihre Teams, ist die Benutzereingabe eines Codes erforderlich, um diese Authentifizierung abschließen zu können. Gemeinsam genutzte Geräte verfügen im Allgemeinen nicht über einen einzelnen Benutzer, der die mehrstufige Authentifizierung konfigurieren und abschließen kann. Außerdem gilt: Wenn das Konto alle x Tage neu authentifiziert werden muss, kann ein freigegebenes Gerät die Herausforderung nicht ohne Eingreifen eines Benutzers lösen.

Die mehrstufige Authentifizierung wird bei gemeinsam genutzten Geräten nicht unterstützt. Die Methoden, die Sie stattdessen verwenden möchten, sind nachfolgend aufgeführt.

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>Bewährte Methoden für die Bereitstellung von gemeinsam genutzten Android-Geräten mit Teams

Microsoft empfiehlt die folgenden Einstellungen, wenn Sie Teams in Ihrer Organisation bereitstellen.

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**Verwenden eines Ressourcenkontos und Drosseln des Kennwortablaufs**

Teams gemeinsam genutzten Geräten sollten ein Postfach [für Exchange-Ressourcen verwenden](/exchange/recipients-in-exchange-online/manage-resource-mailboxes). Beim Erstellen dieser Postfächer wird automatisch ein Konto generiert. Diese Konten können entweder mit anderen Konten Azure AD Active Directory synchronisiert oder direkt in einem Azure AD. Alle Kennwortablaufrichtlinien für Benutzer gelten auch für Konten, die auf freigegebenen Geräten Teams verwendet werden. Um Unterbrechungen durch Kennwortablaufrichtlinien zu vermeiden, legen Sie daher die Kennwortablaufrichtlinie für freigegebene Geräte so ein, dass sie nie abläuft.

Beginnend mit Teams-Geräten CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams Version 1449/1.0.94.2021022403 für Teams-Smartphones) und [CY202 Update Nr. 2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams Version 1449/1.0.96.2021051904 für Microsoft Teams-Räume unter Android) können sich Mandantenadministratoren remote bei Teams-Geräten anmelden. Statt Kennwörter für Techniker zum Einrichten von Geräten gemeinsam zu verwenden, sollten Mandantenadministratoren die Remote-Anmeldung zum Ausschreiben von Überprüfungscodes verwenden. Für diese Geräte können Sie sich über das Admin Center Teams anmelden.

Weitere Informationen finden Sie unter [Remotebereitstellung und Anmelden für Teams Android-Geräte](/MicrosoftTeams/devices/remote-provision-remote-login). 

### <a name="review-these-conditional-access-policies"></a>**Überprüfen dieser Richtlinien für bedingten Zugriff**

Azure AD bedingter Zugriff legt zusätzliche Anforderungen fest, die Geräte erfüllen müssen, um sich anmelden zu können. Lesen Teams für alle Geräte die folgenden Richtlinien, um festzustellen, ob Sie die Richtlinien verfasst haben, die es Benutzern gemeinsam genutzter Geräte gestatten, ihre Arbeit zu tun.

> [!TIP]
> Eine Übersicht über bedingten Zugriff finden Sie unter [Was ist bedingter Zugriff](/azure/active-directory/conditional-access/overview)?

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>Verwenden Sie die mehrstufige Authentifizierung nicht für gemeinsam genutzte Geräte.

Konten für gemeinsam genutzte Geräte sind mit einem Raum oder physischen Raum und nicht mit einem Endbenutzerkonto verknüpft. Da freigegebene Geräte die mehrstufige Authentifizierung nicht unterstützen, schließen Sie freigegebene Geräte aus allen Richtlinien für mehrstufige Authentifizierung aus.

>[!TIP]
>Verwenden Sie entweder [benannte Position, oder](/azure/active-directory/conditional-access/location-condition) [fordern Sie kompatible Geräte an](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) , um gemeinsam genutzte Geräte zu sichern.

### <a name="you-can-use-location-based-access-with-named-locations"></a>Sie können standortbasierten Zugriff mit benannten Speicherorten verwenden.

Wenn freigegebene Geräte an einem genau definierten Speicherort bereitgestellt werden, der mit einem Bereich von IP-Adressen identifiziert werden kann, können Sie bedingten [](/azure/active-directory/conditional-access/location-condition) Zugriff mit benannten Speicherorten für diese Geräte konfigurieren. Diese Bedingung erlaubt diesen Geräten den Zugriff auf Ihre Unternehmensressourcen nur, wenn sie sich innerhalb Ihres Netzwerks befinden.

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>Wann und wann keine kompatiblen gemeinsamen Geräte erforderlich sind

>[!NOTE]
>Für die Gerätekonformität ist eine Intune-Lizenz erforderlich.

Wenn Sie freigegebene Geräte bei Intune registrieren, können Sie die Gerätekonformität als Steuerelement im bedingten Zugriff konfigurieren, damit nur kompatible Geräte auf Ihre Unternehmensressourcen zugreifen können. Teams Geräte können basierend auf der Gerätekonformität für Richtlinien für den bedingten Zugriff konfiguriert werden. Weitere Informationen finden Sie unter [Bedingter Zugriff: Konformitäts- oder Hybridzugriff Azure AD angeschlossenes Gerät](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device).

Informationen zum Festlegen von Complianceeinstellungen für Ihre Geräte mit Intune finden Sie unter Verwenden von Compliancerichtlinien zum Festlegen von Regeln für Geräte, [die Sie mit Intune verwalten](/intune/protect/device-compliance-get-started).

>[!NOTE]
> Freigegebene Geräte, die für *"Hot-King" verwendet werden* , sollten von den Compliancerichtlinien ausgeschlossen werden. Compliancerichtlinien verhindern, dass sich die Geräte beim Hot Desk-Benutzerkonto registrieren. **Verwenden Sie stattdessen benannte Speicherorte, um diese Geräte zu schützen**.
> Um die Sicherheit zu erhöhen, können [](/azure/active-directory/authentication/tutorial-enable-azure-mfa) Sie zusätzlich zu den benannten Standortrichtlinien auch die mehrstufige Authentifizierung für Benutzer */* Benutzerkonten mit Hot-King-Benutzern oder -Benutzerkonten erfordern.

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>Ausschließen von geteilten Geräten aus den Bedingungen der Anmeldehäufigkeit

Unter Bedingter Zugriff können Sie [](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) die Anmeldehäufigkeit so konfigurieren, dass Benutzer sich erneut anmelden müssen, um nach einem bestimmten Zeitraum auf eine Ressource zu zugreifen. Wenn bei Raumkonten die Anmeldehäufigkeit erzwungen wird, melden sich die gemeinsam genutzten Geräte ab, bis sie von einem Administrator erneut angemeldet werden. Microsoft empfiehlt, freigegebene Geräte aus den Richtlinien für Anmeldehäufigkeit zu ausschließen.

### <a name="using-filters-for-devices"></a>Verwenden von Filtern für Geräte

[Filter für Geräte sind](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) ein Feature des bedingten Zugriffs, mit dem Sie genauere Richtlinien für Geräte basierend auf geräteeigenschaften konfigurieren können, die in Azure AD. Sie können auch ihre eigenen benutzerdefinierten Werte verwenden, indem Sie Erweiterungsattribute 1 bis 15 für das Geräteobjekt festlegen und diese dann verwenden.

Verwenden Sie Filter für Geräte, um Ihre gemeinsamen Geräte zu identifizieren und Richtlinien in zwei wichtigen Szenarien zu aktivieren:

1.  Ausschließen von geteilten Geräten aus Richtlinien, die für persönliche Geräte angewendet werden. Beispielsweise wird das Erfordern der Gerätekonformität nicht für gemeinsam genutzte Geräte erzwungen, die für die Hot-King-Verwendung verwendet werden, sondern wird für alle anderen Geräte basierend auf der Modellnummer erzwungen. 

2.  Erzwingen von speziellen Richtlinien für gemeinsam genutzte Geräte, *die nicht* auf persönliche Geräte angewendet werden sollen. Beispielsweise, wenn benannte Speicherorte als Richtlinie nur für allgemeine Geräte erforderlich sind, basierend auf einem Erweiterungsattribut, das Sie für diese Geräte festlegen (z. B.: "CommonAreaPhone").

>[!NOTE] 
> Einige Attribute **wie Modell,** **Hersteller** und **operatingSystemVersion** können nur festgelegt werden, wenn Geräte von Intune verwaltet werden. Wenn Ihre Geräte nicht von Intune verwaltet werden, verwenden Sie Erweiterungsattribute.
