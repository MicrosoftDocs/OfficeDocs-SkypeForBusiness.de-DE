---
title: Bewährte Methoden für bedingten Zugriff und Compliance für Microsoft Teams-Räume
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Erfahren Sie mehr über empfohlene Richtlinien für bedingten Zugriff und Intune-Gerätekonformität und bewährte Methoden für Microsoft Teams-Räume.
ms.openlocfilehash: 1f4bec9d47b73be1638b1740afeb879b4dfb4026
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2022
ms.locfileid: "63689143"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>Bedingte Zugriffe und Intune-Compliance für Microsoft Teams-Räume

Dieser Artikel enthält Anforderungen und bewährte Methoden für bedingte Zugriffs- und Intune-Gerätekonformitätsrichtlinien für Microsoft Teams-Räume, die an freigegebenen Plätzen verwendet werden.

## <a name="requirements"></a>Anforderungen

Teams-Räume müssen bereits auf den Geräten bereitgestellt sein, den Sie Richtlinien für bedingten Zugriff zuweisen möchten. Wenn Sie noch keine Teams-Räume bereitgestellt haben, finden Sie weitere Informationen unter Erstellen von Ressourcenkonten für Räume und freigegebene [Teams-Geräte](with-office-365.md) und Bereitstellen Microsoft Teams-Räume [unter Android](../devices/collab-bar-deploy.md).

Für Azure Active Directory bedingten Zugriff ist ein P1-Serviceplan erforderlich. Sie ist in der Lizenz Microsoft Teams-Räume enthalten.

## <a name="teams-rooms-conditional-access-best-practices"></a>Teams-Räume bewährte Methoden für den bedingten Zugriff

Richtlinien für bedingten Zugriff können den Anmeldevorgang auf Geräten sichern, die sich an freigegebenen Plätzen befinden und von mehreren Personen verwendet werden. Eine Übersicht über bedingten Zugriff in Azure Active Directory (Azure AD) finden Sie unter Was ist bedingter Zugriff [in Azure Active Directory?](/azure/active-directory/conditional-access/overview).

Beachten Sie bei der Verwendung von bedingter Teams-Räume zum Sichern Ihrer Daten die folgenden bewährten Methoden:

-   Um die Bereitstellung und Verwaltung zu vereinfachen, schließen Sie alle mit Microsoft 365 verknüpften Raumressourcenkonten Teams-Räume einer Benutzergruppe ein.

-   Verfügen Sie über einen Benennungsstandard für Teams-Räume Ressourcenkonten. Beispielsweise beginnen die Kontonamen "mtr-room1@contoso.com" und "mtr-room2@contoso.com" jeweils mit dem Präfix "mtr-".
    Wenn Kontonamen standardisiert sind, können Sie dynamische Gruppen in Azure AD um Richtlinien für bedingten Zugriff automatisch auf alle diese Konten auf einmal anzuwenden. Weitere [Informationen zu dynamischen Gruppen finden](/azure/active-directory/enterprise-users/groups-dynamic-membership) Sie unter Regeln für die Mitgliedschaft bei dynamisch ausgefüllten Gruppen.

Eine Liste der unterstützten Zuweisungen für bedingten Zugriff für Teams-Räume Finden Sie unter Unterstützte [Richtlinien für bedingten Zugriff](supported-ca-and-compliance-policies.md#supported-conditional-access-policies).

## <a name="example-conditional-access-policy"></a>Beispiel für eine Richtlinie für bedingten Zugriff

Im folgenden Beispiel funktioniert die Richtlinie für bedingten Zugriff wie folgt:

1.  Das Konto, mit dem Sie sich anmelden, muss Ein Mitglied einer bestimmten Benutzergruppe sein, in diesem Beispiel der Gruppe "Freigegebene Geräte".

2.  Das Konto, mit dem sie sich anmelden, darf nur versuchen, auf ihre Exchange Online, Microsoft Teams oder SharePoint zu greifen. Versuche, sich bei einer anderen Client-App zu anmelden, werden abgelehnt.

3.  Das Ressourcenkonto muss sich bei der Windows anmelden.

4.  Das Ressourcenkonto muss sich auch von einem bekannten, vertrauenswürdigen Speicherort anmelden.

Wenn diese Bedingungen erfolgreich erfüllt werden und der Benutzer den richtigen Benutzernamen und das richtige Kennwort ein gibt, wird das Ressourcenkonto bei der Teams.

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Bedingter Zugriff mit Microsoft Intune für Teams-Räume

Complianceanforderungen sind definierte Regeln, die Geräte erfüllen müssen, um als konform gekennzeichnet zu werden, z. B. die Mindestversion des Betriebssystems. Geräte müssen als konform betrachtet werden, bevor sie für die Anmeldung bei einem Ressourcenkonto verwendet werden können.

Eine Liste der unterstützten Intune-Compliancerichtlinien für Teams-Räume finden Sie unter Unterstützte [Richtlinien zur Gerätekonformität](supported-ca-and-compliance-policies.md#supported-device-compliance-policies).

Weitere Informationen zum Einrichten von Intune mit Teams Android-Geräten finden Sie unter Konfigurieren von Intune zum Registrieren [Teams Android-basierten Geräten](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices).

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>Beispiel (nur Windows): Bedingter Zugriff mit Intune-Gerätekonformität

In diesem Beispiel wird für Teams-Räume -Windows

1. Erfordert, dass eine Firewall auf einem computer Teams-Räume ausgeführt Windows.

2. Microsoft Defender muss auf ihrem Teams-Räume.

3. Wenn ein Teams einer dieser Anforderungen nicht erfüllt, wird er nicht als konform gekennzeichnet, und die Geräte melden sich nicht an.

Diese Compliancerichtlinie gilt für alle Benutzer, nicht nur für Teams Ressourcenkonten.
