---
title: Bewährte Methoden für bedingten Zugriff und Compliance für Microsoft Teams-Räume
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Erfahren Sie mehr über die empfohlenen Richtlinien für bedingten Zugriff und Intune Gerätecompliance sowie bewährte Methoden für Microsoft Teams-Räume.
ms.openlocfilehash: 1221060121f47154549c6c6fc926415f4feabbe5
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761307"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>Bedingter Zugriff und Intune Compliance für Microsoft Teams-Räume

Dieser Artikel enthält Anforderungen und bewährte Methoden für bedingten Zugriff und Intune Gerätekompatibilitätsrichtlinien für Microsoft Teams-Räume, die in freigegebenen Räumen verwendet werden.

## <a name="requirements"></a>Anforderungen

Teams-Räume müssen bereits auf den Geräten bereitgestellt werden, den Sie Richtlinien für bedingten Zugriff zuweisen möchten. Wenn Sie Teams-Räume noch nicht bereitgestellt haben, finden Sie weitere Informationen unter ["Erstellen von Ressourcenkonten für Räume und freigegebene Teams Geräte](with-office-365.md)" und "[Bereitstellen von Microsoft Teams-Räume auf Android](../devices/collab-bar-deploy.md)".

Für die Verwendung des bedingten Zugriffs ist ein Azure Active Directory P1-Serviceplan erforderlich. Es ist in der Microsoft Teams-Räume-Lizenz enthalten.

## <a name="teams-rooms-conditional-access-best-practices"></a>bewährte Methoden für den Teams-Räume bedingten Zugriff

Richtlinien für bedingten Zugriff können den Anmeldevorgang auf Geräten sichern, die sich in freigegebenen Räumen befinden und von mehreren Personen verwendet werden. Eine Übersicht über den bedingten Zugriff in Azure Active Directory (Azure AD) finden Sie unter [Was ist bedingter Zugriff in Azure Active Directory?](/azure/active-directory/conditional-access/overview).

Berücksichtigen Sie bei verwendung des bedingten Zugriffs zum Sichern Teams-Räume die folgenden bewährten Methoden:

-   Um die Bereitstellung und Verwaltung zu vereinfachen, schließen Sie alle Microsoft 365 Raumressourcenkonten, die Teams-Räume zugeordnet sind, in einer Benutzergruppe ein.

-   Verwenden Sie einen Benennungsstandard für alle Teams-Räume Ressourcenkonten. Beispielsweise beginnen die Kontonamen "mtr-room1@contoso.com" und "mtr-room2@contoso.com" beide mit dem Präfix "mtr-".
    Wenn Kontonamen standardisiert sind, können Sie dynamische Gruppen in Azure AD verwenden, um automatisch Richtlinien für bedingten Zugriff auf alle diese Konten gleichzeitig anzuwenden. Weitere Informationen zu dynamischen Gruppen finden Sie unter [Regeln für die Mitgliedschaft dynamisch ausgefüllter Gruppen](/azure/active-directory/enterprise-users/groups-dynamic-membership) .

Eine Liste der unterstützten Zuweisungen für bedingten Zugriff für Teams-Räume finden Sie unter ["Unterstützte Richtlinien für bedingten Zugriff"](supported-ca-and-compliance-policies.md#supported-conditional-access-policies).

## <a name="example-conditional-access-policy"></a>Beispielrichtlinie für bedingten Zugriff

Im folgenden Beispiel funktioniert die Richtlinie für bedingten Zugriff wie folgt:

1.  Das Konto, das sich anmeldet, muss Mitglied einer bestimmten Benutzergruppe sein, in diesem Beispiel der Gruppe "Freigegebene Geräte".

2.  Das Konto, das sich anmeldet, darf nur versuchen, auf Exchange Online, Microsoft Teams oder SharePoint Online zuzugreifen. Versuche, sich bei einer anderen Client-App anzumelden, werden abgelehnt.

3.  Das Ressourcenkonto muss sich auf der Windows Geräteplattform anmelden.

4.  Das Ressourcenkonto muss sich auch von einem bekannten, vertrauenswürdigen Speicherort aus anmelden.

Wenn diese Bedingungen erfolgreich erfüllt sind und der Benutzer den richtigen Benutzernamen und das richtige Kennwort eingibt, wird sich das Ressourcenkonto bei Teams anmelden.

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Bedingter Zugriff mit Microsoft Intune Compliance für Teams-Räume

Complianceanforderungen sind definierte Regeln, die Geräte erfüllen müssen, um als konform gekennzeichnet zu werden, z. B. die Mindestversion des Betriebssystems. Geräte müssen als konform betrachtet werden, bevor sie für die Anmeldung bei einem Ressourcenkonto verwendet werden können.

Eine Liste der unterstützten Intune Compliancerichtlinien für Teams-Räume finden Sie unter [Unterstützte Gerätecompliancerichtlinien](supported-ca-and-compliance-policies.md#supported-device-compliance-policies).

Weitere Informationen zum Einrichten von Intune mit Teams Android-Geräten finden [Sie unter Konfigurieren Intune zum Registrieren Teams Android-basierter Geräte](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices).

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>Beispiel (nur Windows): Bedingter Zugriff mit Intune Gerätekompatibilität

In diesem Beispiel für Teams-Räume auf Windows

1. Eine Firewall muss auf Teams-Räume auf Windows ausgeführt werden.

2. Setzen Sie voraus, dass Microsoft Defender auf Teams-Räume ausgeführt wird.

3. Wenn ein Teams Raum keine dieser Anforderungen erfüllt, wird er nicht als konform gekennzeichnet, und die Geräte melden sich nicht an.

Diese Compliancerichtlinie gilt für alle Benutzer, nicht nur für Teams Ressourcenkonten.
