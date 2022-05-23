---
title: Bewährte Methoden für die Authentifizierung für Microsoft Teams gemeinsam genutzte Geräteverwaltung von Android Geräten.
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Bewährte Methoden für die verwaltung gemeinsam genutzter Android-Geräte in Teams. Dies umfasst bedingten Zugriff, Kennwortrichtlinien, Ratschläge zur mehrstufigen Authentifizierung und vieles mehr.
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
ms.openlocfilehash: 6eef76052f662b26f946bf80839a62186c287b68
ms.sourcegitcommit: d425748a50964ebc78e5d38fce564a444a449f43
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2022
ms.locfileid: "65635463"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>Bewährte Methoden für die Authentifizierung für Teams gemeinsam genutzte Geräteverwaltung auf Android Geräten

Die Ziele von Geräten, die mit Teams verwendet werden, machen unterschiedliche Geräteverwaltungsstrategien erforderlich. Beispielsweise hat ein persönliches Geschäftstablett, das von einem einzelnen Vertriebsmitarbeiter verwendet wird, einen anderen Satz von Anforderungen als ein Telefon mit Einem Anruf, das von vielen Kundendienstmitarbeitern geteilt wird.

Sicherheitsadministratoren und Betriebsteams müssen die Geräte planen, die in der Organisation verwendet werden können. Sie müssen *Sicherheitsmaßnahmen* implementieren, die für jeden Zweck am besten geeignet sind. Die Empfehlungen dieses Artikels erleichtern einige dieser Entscheidungen.

>[!NOTE]
>Der bedingte Zugriff erfordert ein Azure Active Directory (Azure AD) Premium Abonnement.

>[!NOTE]
>Richtlinien für Android mobile Geräte gelten möglicherweise nicht für Teams Android Geräte.

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>Authentifizierungsempfehlungen unterscheiden sich bei persönlichen im Vergleich zu freigegebenen Android-Geräten

Freigegebene Teams Geräte können nicht dieselben Anforderungen für Registrierung und Compliance wie auf persönlichen Geräten verwenden. Das Anwenden von Authentifizierungsanforderungen für persönliche Geräte auf freigegebene Geräte führt zu Anmeldeproblemen.

1.  **Geräte sind aufgrund von Kennwortrichtlinien abgemeldet.**

Konten, die auf Teams Geräten verwendet werden, verfügen über eine Kennwortablaufrichtlinie. Die Konten, die mit freigegebenen Geräten verwendet werden, verfügen nicht über einen bestimmten Benutzer, der sie aktualisieren und in einen funktionierenden Zustand wiederherstellen kann, wenn ihre Kennwörter ablaufen. Wenn Ihre Organisation erfordert, dass Kennwörter ablaufen und gelegentlich zurückgesetzt werden, funktionieren diese Konten nicht mehr auf Teams Geräten, bis ein Teams Administrator das Kennwort zurücksetzt und sich wieder anmeldet.

**Herausforderung**: Wenn es um den Zugriff geht. Teams von einem Gerät aus verfügt das Konto einer Person über eine Kennwortablaufrichtlinie. Wenn das Kennwort abläuft, wird es einfach geändert. Konten, die auf *freigegebenen Geräten* (Ressourcenkonten) verwendet werden, sind jedoch möglicherweise nicht mit einer einzelnen Person verbunden, die ein Kennwort nach Bedarf ändern kann. Dies bedeutet, dass ein Kennwort abläuft und mitarbeiter vor Ort bleiben kann, ohne zu wissen, wie sie ihre Arbeit fortsetzen können.

Wenn Ihre Organisation eine Kennwortzurücksetzung erfordert oder den Ablauf des Kennworts erzwingt, stellen Sie sicher, dass ein Teams Administrator bereit ist, das Kennwort zurückzusetzen, damit sich diese freigegebenen Konten wieder anmelden können.

2.  **Geräte können sich aufgrund von Richtlinien für bedingten Zugriff nicht anmelden.**

**Herausforderung**: Freigegebene Geräte können nicht den Azure AD-Richtlinien für bedingten Zugriff für Benutzerkonten oder persönliche Geräte entsprechen. Wenn freigegebene Geräte mit Benutzerkonten oder persönlichen Geräten für eine Richtlinie für bedingten Zugriff gruppiert sind, schlägt die Anmeldung *fehl*.

Wenn z. B. die mehrstufige Authentifizierung für den Zugriff auf Teams erforderlich ist, ist die Benutzereingabe eines Codes erforderlich, um diese Authentifizierung abzuschließen. Für freigegebene Geräte gibt es in der Regel keinen einzelnen Benutzer, der die mehrstufige Authentifizierung konfigurieren und abschließen kann. Wenn das Konto alle X Tage erneut authentifiziert werden muss, kann ein freigegebenes Gerät die Herausforderung auch nicht ohne Eingreifen des Benutzers lösen.

Die mehrstufige Authentifizierung wird auf gemeinsam genutzten Geräten nicht unterstützt. Die stattdessen zu verwendenden Methoden sind unten beschrieben.

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>Bewährte Methoden für die Bereitstellung von gemeinsam genutzten Android-Geräten mit Teams

Microsoft empfiehlt die folgenden Einstellungen bei der Bereitstellung Teams Geräten in Ihrer Organisation.

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**Verwenden eines Ressourcenkontos und Einschränken des Kennwortablaufs**

Teams freigegebenen Geräte sollten ein [Exchange Ressourcenpostfach](/exchange/recipients-in-exchange-online/manage-resource-mailboxes) verwenden. Durch das Erstellen dieser Postfächer wird automatisch ein Konto generiert. Diese Konten können entweder aus Active Directory mit Azure AD synchronisiert oder direkt in Azure AD erstellt werden. Alle Kennwortablaufrichtlinien für Benutzer gelten auch für Konten, die auf Teams freigegebenen Geräten verwendet werden. Um Unterbrechungen durch Kennwortablaufrichtlinien zu vermeiden, legen Sie daher die Kennwortablaufrichtlinie für freigegebene Geräte so fest, dass sie nie abläuft.

Ab Teams Geräten CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams Version 1449/1.0.94.2021022403 für Teams Smartphones) und [CY20 21 Update Nr. 2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams Version 1449/1.0.96.2021051904 für Microsoft Teams-Räume auf Android), können sich Mandantenadministratoren anmelden Teams Geräte remote aus. Anstatt Kennwörter für Techniker zum Einrichten von Geräten freizugeben, sollten Mandantenadministratoren die Remoteanmeldung verwenden, um Überprüfungscodes auszustellen. Die Anmeldung kann für diese Geräte über das Teams Admin Center erfolgen.

Weitere Informationen finden Sie unter [Remotebereitstellung und -anmeldung für Teams Android Geräte](/MicrosoftTeams/devices/remote-provision-remote-login). 

### <a name="review-these-conditional-access-policies"></a>**Überprüfen Sie diese Richtlinien für bedingten Zugriff**

Der bedingte Azure AD-Zugriff legt zusätzliche Anforderungen fest, die Geräte erfüllen müssen, um sich anzumelden. Lesen Sie für Teams Geräte die nachstehenden Anleitungen, um festzustellen, ob Sie die Richtlinien erstellt haben, mit denen Benutzer freigegebener Geräte ihre Arbeit erledigen können.

> [!TIP]
> Eine Übersicht über bedingten Zugriff finden Sie unter [Was ist bedingter Zugriff](/azure/active-directory/conditional-access/overview)?

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>Verwenden Sie keine mehrstufige Authentifizierung für freigegebene Geräte

Konten für freigegebene Geräte sind mit einem Raum oder physischen Raum und nicht mit einem Endbenutzerkonto verknüpft. Da freigegebene Geräte die mehrstufige Authentifizierung nicht unterstützen, schließen Sie freigegebene Geräte von allen mehrstufigen Authentifizierungsrichtlinien aus.

>[!TIP]
>Verwenden Sie entweder [einen benannten Speicherort](/azure/active-directory/conditional-access/location-condition) oder [ein kompatibles Gerät](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) , um freigegebene Geräte zu schützen.

### <a name="you-can-use-location-based-access-with-named-locations"></a>Sie können den standortbasierten Zugriff mit benannten Speicherorten verwenden.

Wenn freigegebene Geräte an einem klar definierten Speicherort bereitgestellt werden, der mit einem Bereich von IP-Adressen identifiziert werden kann, können Sie den bedingten Zugriff [mithilfe von benannten Speicherorten](/azure/active-directory/conditional-access/location-condition) für diese Geräte konfigurieren. Diese Bedingung ermöglicht es diesen Geräten, nur dann auf Ihre Unternehmensressourcen zuzugreifen, wenn sie sich in Ihrem Netzwerk befinden.

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>Wann und wann keine kompatiblen gemeinsam genutzten Geräte erforderlich sind

>[!NOTE]
>Für die Gerätekompatibilität ist eine Intune Lizenz erforderlich.

Wenn Sie freigegebene Geräte in Intune registrieren, können Sie die Gerätekompatibilität als Steuerelement im bedingten Zugriff konfigurieren, sodass nur kompatible Geräte auf Ihre Unternehmensressourcen zugreifen können. Teams Geräte können basierend auf der Gerätekompatibilität für Richtlinien für bedingten Zugriff konfiguriert werden. Weitere Informationen finden Sie [unter Bedingter Zugriff: Kompatibles oder hybrides Azure AD-verbundenes Gerät erforderlich](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device).

Informationen zum Festlegen der Complianceeinstellung für Ihre Geräte mithilfe von Intune finden [Sie unter Verwenden von Compliancerichtlinien zum Festlegen von Regeln für Geräte, die Sie mit Intune verwalten](/intune/protect/device-compliance-get-started).

>[!NOTE]
> Freigegebene Geräte, die für *hot desking* verwendet werden, sollten von Compliancerichtlinien ausgeschlossen werden. Compliancerichtlinien verhindern, dass sich die Geräte beim Hot desk-Benutzerkonto registrieren. **Verwenden Sie stattdessen benannte Speicherorte, um diese Geräte zu sichern**.
> Um die Sicherheit zu erhöhen, können Sie zusätzlich zu den benannten Standortrichtlinien auch [die mehrstufige Authentifizierung](/azure/active-directory/authentication/tutorial-enable-azure-mfa) für *hot desking-Benutzer/Benutzerkonten* anfordern.

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>Ausschließen freigegebener Geräte von Anmeldehäufigkeitsbedingungen

Im bedingten Zugriff können Sie die [Anmeldehäufigkeit so konfigurieren](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) , dass Benutzer sich erneut anmelden müssen, um nach einem bestimmten Zeitraum auf eine Ressource zuzugreifen. Wenn die Anmeldehäufigkeit für Raumkonten erzwungen wird, melden sich freigegebene Geräte ab, bis sie von einem Administrator erneut angemeldet sind. Microsoft empfiehlt, freigegebene Geräte von allen Anmeldehäufigkeitsrichtlinien auszuschließen.

### <a name="using-filters-for-devices"></a>Verwenden von Filtern für Geräte

[Filter für Geräte](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) ist ein Feature im bedingten Zugriff, mit dem Sie detailliertere Richtlinien für Geräte basierend auf den in Azure AD verfügbaren Geräteeigenschaften konfigurieren können. Sie können auch eigene benutzerdefinierte Werte verwenden, indem Sie die Erweiterungsattribute 1 bis 15 für das Geräteobjekt festlegen und diese dann verwenden.

Verwenden Sie Filter für Geräte, um Ihre Geräte im einheitlichen Bereich zu identifizieren und Richtlinien in zwei wichtigen Szenarien zu aktivieren:

1.  Ausschließen von freigegebenen Geräten aus Richtlinien, die für persönliche Geräte angewendet wurden. Beispielsweise wird die Anforderung der Gerätekompatibilität *nicht für freigegebene Geräte erzwungen* , die für die Hot-Desking verwendet werden, sondern für alle anderen Geräte basierend auf der Modellnummer *erzwungen* .

2.  Erzwingen spezieller Richtlinien auf freigegebenen Geräten, die nicht auf persönliche Geräte angewendet werden *sollten* . Beispielsweise müssen benannte Speicherorte als Richtlinie nur für Geräte mit gemeinsamem Bereich basierend auf einem Erweiterungsattribut benötigt werden, das Sie für diese Geräte festgelegt haben (z. B.: "CommonAreaPhone").

>[!NOTE] 
> Einige Attribute wie **Modell**, **Hersteller** und **operatingSystemVersion** können nur festgelegt werden, wenn Geräte von Intune verwaltet werden. Wenn Ihre Geräte nicht von Intune verwaltet werden, verwenden Sie Erweiterungsattribute.
