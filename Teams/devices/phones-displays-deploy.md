---
title: Bereitstellen von Teams-Smartphones und-Teams mit InTune
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: Dieser Artikel enthält eine Übersicht über die von Microsoft Teams unterstützten Funktionen und Features.
ms.openlocfilehash: acebf619d76cd6df2f0da305deedec9dd3b79aa0
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787617"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Bereitstellen von Teams-Smartphones und-Teams mit InTune

In diesem Artikel erhalten Sie einen Überblick über die Bereitstellung von Teams-Smartphones und-Teams mithilfe von InTune.

## <a name="conditional-access"></a>Bedingter Zugriff

Bedingter Zugriff ist eine Azure Active Directory (Azure AD)-Funktion, mit der Sie sicherstellen können, dass Geräte, die auf Ihre Office 365-Ressourcen zugreifen, ordnungsgemäß verwaltet und sicher sind.  Wenn Sie Richtlinien für den bedingten Zugriff auf den Team Dienst anwenden, werden Android-Geräte (einschließlich Teams-Smartphones und-Teams angezeigt), die Access-Teams für InTune registrieren müssen, und Ihre Einstellungen müssen ihren Richtlinien entsprechen.  Wenn das Gerät nicht für InTune registriert ist oder wenn es registriert ist, seine Einstellungen aber nicht Ihren Richtlinien entsprechen, verhindert der bedingte Zugriff, dass sich ein Benutzer bei oder mithilfe der Teams-App auf dem Gerät anmeldet.

In der Regel werden Konformitätsrichtlinien, die in InTune definiert sind, Gruppen von Benutzern zugewiesen.  Das bedeutet: Wenn Sie user@contoso.com eine Android-Konformitätsrichtlinie zuweisen, gilt diese Richtlinie gleichermaßen für Ihr Android-Smartphone sowie für alle Android-basierten Teams, die sich in user@contoso.com anmelden.

Wenn Sie den bedingten Zugriff verwenden, für den die Intune-Registrierung erzwungen werden muss, müssen Sie in Ihrer Organisation ein paar Dinge einrichten, um eine erfolgreiche InTune-Registrierung zu ermöglichen:

- **InTune-Lizenz** Der Benutzer, der sich beim Team-Gerät anmeldet, muss für InTune lizenziert sein.  Solange das Team-Gerät bei einem Benutzerkonto angemeldet ist, das über eine gültige InTune-Lizenz verfügt, wird das Gerät im Rahmen des Anmeldeprozesses automatisch für Microsoft InTune registriert.
- **Konfigurieren von InTune** Für die Registrierung des Android-Geräte Administrators muss ein ordnungsgemäß konfigurierter InTune-Mandant eingerichtet sein.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Konfigurieren von InTune zum Registrieren von Android-basierten Geräten für Teams

Auf Android-Geräten basierende Teams werden über die Verwaltung von Android Device Administrator (da) in InTune verwaltet. Bevor Sie Geräte für InTune registrieren können, müssen Sie einige grundlegende Schritte ausführen.  Wenn Sie bereits heute Geräte mit InTune verwalten, haben Sie wahrscheinlich bereits alle diese Vorgänge ausgeführt.  Wenn dies nicht der Fall ist, gehen Sie wie folgt vor:

1. Stellen Sie die Intune-MDM-Autorität (Mobile Device Management) ein.  Wenn Sie InTune noch nie zuvor verwendet haben, müssen Sie die MDM-Autorität einrichten, bevor Sie Geräte registrieren können. Weitere Informationen finden Sie unter [Einrichten der Verwaltung mobiler Geräte](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set).  Hierbei handelt es sich um einen einmaligen Schritt, der beim Erstellen eines neuen InTune-Mandanten durchgeführt werden muss.
2. Aktivieren Sie die Registrierung des Android-Geräte Administrators. Android-basierte Teams-Geräte werden als Geräteadministrator Geräte mit InTune verwaltet.  Die Registrierung für den Geräteadministrator ist standardmäßig für neu erstellte Mandanten deaktiviert.  Weitere Informationen finden Sie unter [Administrator Registrierung für Android-Geräte](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator).
3. Zuweisen von Lizenzen zu Benutzern Benutzern von Teams-Geräten, die sich für InTune registrieren, muss eine gültige InTune-Lizenz zugewiesen werden. Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzern, damit diese Geräte in InTune registrieren können](https://docs.microsoft.com/intune/fundamentals/licenses-assign).
4. Zuweisen von Konformitätsrichtlinien für geräteadministratoren  Erstellen Sie eine Konformitätsrichtlinie für Android-geräteadministratoren, und weisen Sie Sie der Azure Active Directory-Gruppe zu, die die Benutzer enthält, die sich bei den Teams-Geräten anmelden werden. Weitere Informationen finden Sie unter [Verwenden von Konformitätsrichtlinien zum Einrichten von Regeln für Geräte, die Sie mit InTune verwalten](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>Weitere Informationen

[Telefone für Teams](phones-for-teams.md)

[Für Microsoft Teams zertifizierte IP-Telefone](teams-ip-phones.md)

[Teams wird angezeigt](teams-displays.md)

[Verwalten Ihrer Geräte in Teams](device-management.md).

[Marketplace für Teams](https://office.com/teamsdevices)
