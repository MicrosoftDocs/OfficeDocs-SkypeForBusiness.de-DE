---
title: Anmelden bei Teams mit moderner Authentifizierung
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Hier erfahren Sie, wie die moderne Authentifizierung funktioniert, wie Sie zwischen Konten wechseln und wie Sie Probleme mit der modernen Authentifizierung behandeln. Erläutert auch, wie man Teams anweisen kann, das Vorausfüllen des Benutzernamens (UPN) bei der Anmeldung zu ignorieren.
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32e231fbcef2991e13ec5b496e6ed61eb677ee20
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665757"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Anmelden bei Microsoft Teams mit moderner Authentifizierung
==========================

Microsoft empfiehlt Unternehmen, neuere Versionen von Windows 10 mit Hybrid Domain Join- oder Azure AD Join-Konfiguration zu verwenden. Dadurch wird sichergestellt, dass die Nutzerkonten im Windows-Webkonto-Manager vorbereitet werden, wodurch wiederum die einmalige Anmeldung bei Teams und anderen Microsoft-Anwendungen ermöglicht wird. Dies bietet eine bessere Benutzererfahrung (stille Anmeldung) und eine bessere Sicherheitslage.

Microsoft Teams verwendet moderne Authentifizierung, um die Anmeldung einfach und sicher zu gestalten. Um zu erfahren, wie sich Benutzer bei Teams anmelden, lesen Sie bitte [Anmelden in Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>So funktioniert moderne Authentifizierung

Bei der modernen Authentifizierung handelt es sich um einen Prozess, der Teams mitteilt, dass Benutzer ihre Anmeldeinformationen (wie Ihre geschäftliche E-Mail-Adresse und das Kennwort) bereits anderswo eingegeben haben, und dass Sie diese nicht erneut eingeben müssen, um die App zu starten. Das Erlebnis hängt von einigen Faktoren ab, beispielsweise wenn Benutzer mit Windows oder auf einem Mac arbeiten. Es hängt auch davon ab, ob Ihre Organisation die einstufige Authentifizierung oder die mehrstufige Authentifizierung aktiviert hat (die mehrstufige Authentifizierung umfasst in der Regel die Überprüfung von Anmeldeinformationen über ein Telefon, die Eingabe eines eindeutigen Codes, die Eingabe eines PIN-Codes oder die Verwendung eines Fingerabdrucks). Hier ist eine Übersicht über jedes Szenario moderner Authentifizierung.

### <a name="windows-users"></a>Windows-Benutzer

- Wenn sich Nutzer bereits mit ihrem Arbeits- oder Schulkonto bei Windows oder anderen Office-Apps angemeldet haben, werden sie beim Starten von Teams direkt zur App weitergeleitet. Sie müssen ihre Anmeldeinformationen nicht eingeben.

- Microsoft empfiehlt die Verwendung von Windows 10 Version 1903 oder höher, um die beste Single Sign-On-Erfahrung zu erzielen.

- Wenn Nutzer an keiner anderen Stelle in ihrem Microsoft-Arbeits- oder Schulkonto angemeldet sind, werden sie beim Starten von Teams aufgefordert, entweder eine Einzelfaktor- oder eine Multifaktor-Authentifizierung (SFA oder MFA) bereitzustellen, je nachdem, was Ihre Organisation entschieden hat, was der Prozess beinhalten soll.

- Wenn Benutzer bei einem domänengebundenen Computer angemeldet sind, werden sie beim Start von Teams möglicherweise aufgefordert, einen weiteren Authentifizierungsschritt durchzuführen, je nachdem, ob sich Ihre Organisation für MFA entschieden hat oder ob ihr Computer bereits MFA zum Anmelden erfordert. Wenn ihr Computer bereits MFA zur Anmeldung erfordert, startet die App automatisch, wenn  sie Teams öffnen.

- Auf PCs, die einer Domain zugehören, kann Teams den Anmeldebildschirm vorab mit dem Nutzerprinzipalnamen (UPN) füllen, wenn SSO nicht möglich ist. Es gibt Fälle, in denen Sie dies möglicherweise nicht möchten, insbesondere wenn Ihre Organisation verschiedene UPNs lokal und in Azure Active Directory verwendet. In diesem Fall können Sie den folgenden Windows-Registrierungsschlüssel verwenden, um die Vorbelegung des UPN zu deaktivieren:

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > Das Überspringen oder Ignorieren des Vorab-Ausfüllens von Benutzernamen ist für Benutzernamen, die in „.local“ oder „.corp“ enden, standardmäßig aktiviert, daher müssen Sie keinen Registrierungsschlüssel festlegen, um diese zu deaktivieren.


### <a name="mac-users"></a>Mac-Benutzer

Unter MacOS werden Teams Benutzer auffordern, ihren Benutzernamen und ihre Anmeldeinformationen einzugeben, und je nach den Einstellungen Ihres Unternehmens werden Sie möglicherweise zur Multifaktor-Authentifizierung aufgefordert. Sobald die Benutzer ihre Anmeldeinformationen eingegeben haben, werden sie nicht mehr aufgefordert, sie erneut anzugeben. Von diesem Zeitpunkt an startet Teams automatisch, wenn sie am gleichen Computer arbeiten.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Kontowechsel nach Abschluss der modernen Authentifizierung

Wenn Benutzer an einem domänengebundenen Computer arbeiten (z.B. wenn ihr Mandant Kerberos aktiviert hat), können sie nach Abschluss der modernen Authentifizierung nicht mehr zwischen Benutzerkonten wechseln. Wenn Benutzer nicht an einem domänengebundenen Computer arbeiten, können sie zwischen Konten wechseln.

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>Abmeldung von Microsoft Teams nach Abschluss der modernen Authentifizierung

Um sich von Teams abzumelden, können Benutzer auf ihr Profilbild oben in der App klicken und dann **Abmelden** wählen. Sie können auch mit der rechten Maustaste auf das App-Symbol in der Taskleiste klicken und dann **Abmelden** wählen. Sobald sie sich von Teams abgemeldet haben, müssen sie ihre Anmeldeinformationen erneut eingeben, um die App zu starten.

## <a name="urls-and-ip-address-ranges"></a>URLs und IP-Adressbereiche

Microsoft Teams setzt eine Internetverbindung voraus. Informationen zu Endpunkten, die für Kunden mit Microsoft Teams in Microsoft 365- oder Office 365-Plänen sowie für Behörden und andere Clouds erreichbar sein sollten, finden Sie unter [URLs und IP-Adressbereiche für Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

> [!IMPORTANT]
> Microsoft Teams benötigt derzeit Zugriff (TCP-Port 443) auf den Google ssl.gstatic.com-Dienst (<https://ssl.gstatic.com)> für alle Benutzer. Dies gilt selbst dann, wenn Sie Gstatic nicht verwenden. Diese Anforderung wird demnächst (erste Hälfte 2020) aus Microsoft Teams entfernt. Dieser Artikel wird dann entsprechend aktualisiert.

## <a name="troubleshooting-modern-authentication"></a>Problembehandlung bei der modernen Authentifizierung

Die moderne Authentifizierung ist für jede Organisation, die Teams verwendet, verfügbar. Wenn Nutzer den Vorgang nicht abschließen können, stimmt möglicherweise etwas mit Ihrer Domain oder dem Microsoft-Arbeits- oder Schulkonto Ihrer Organisation nicht.

Weitere Informationen finden Sie unter [Wieso habe ich Probleme bei der Anmeldung bei Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).
