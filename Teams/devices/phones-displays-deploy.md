---
title: Bereitstellen von Telefonen und Anzeigen in Teams mithilfe von Intune
ms.author: v-cichur
author: cichur
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
description: Dieser Artikel bietet eine Übersicht über die von Microsoft Teams unterstützten Features.
ms.openlocfilehash: 4d955db2f260af0eff3d0c1f059461703cf23d79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825415"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Bereitstellen von Telefonen und Anzeigen in Teams mithilfe von Intune

Dieser Artikel enthält eine Übersicht über die Bereitstellung von Telefonen und Anzeigen in Teams mit Intune.

## <a name="conditional-access"></a>Bedingter Zugriff

Der bedingte Zugriff ist ein Azure Active Directory (Azure AD)-Feature, mit dem Sie sicherstellen können, dass Geräte, die auf Ihre Office 365-Ressourcen zugreifen, ordnungsgemäß verwaltet werden und sicher sind.  Wenn Sie Richtlinien für bedingten Zugriff auf den Teams-Dienst anwenden, müssen Android-Geräte (einschließlich Teams-Telefonen und Teams-Anzeigen), die auf Teams zugreifen, bei Intune registriert sein, und deren Einstellungen müssen Ihren Richtlinien entsprechen.  Wenn das Gerät nicht bei Intune registriert ist oder wenn es registriert ist, seine Einstellungen aber nicht Ihren Richtlinien entsprechen, verhindert bedingter Zugriff, dass sich ein Benutzer bei der App "Teams" auf dem Gerät anmelden oder diese verwenden kann.

In der Regel werden in Intune definierte Compliancerichtlinien Benutzergruppen zugewiesen.  Dies bedeutet: Wenn Sie user@contoso.com eine Android-Compliancerichtlinie zuweisen, gilt diese Richtlinie gleichermaßen für ihr Android-Smartphone und jedes Android-basierte Teams-Gerät, bei dem user@contoso.com ist.

Wenn Sie den bedingten Zugriff verwenden, für den die Registrierung von Intune erzwungen werden muss, müssen Sie in Ihrer Organisation ein paar Dinge einrichten, um eine erfolgreiche Registrierung von Intune zu ermöglichen:

- **Intune-Lizenz** Der Benutzer, der sich beim Gerät in Teams angemeldet hat, muss für Intune lizenziert sein.  Solange das Gerät bei einem Benutzerkonto angemeldet ist, das über eine gültige Intune-Lizenz verfügt, wird das Gerät im Rahmen des Anmeldevorgangs automatisch bei Microsoft Intune registriert.
- **Konfigurieren von Intune** Sie müssen einen ordnungsgemäß konfigurierten Intune-Mandanten für die Registrierung durch den Android-Geräteadministrator eingerichtet haben.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Konfigurieren von Intune für die Registrierung von Android-basierten Teams-Geräten

Android-basierte Geräte in Teams werden in Intune über die Verwaltung durch den Android-Geräteadministrator (DA) verwaltet. Bevor Geräte bei Intune registriert werden können, müssen Sie ein paar grundlegende Schritte ausführen.  Wenn Sie bereits heute Geräte mit Intune verwalten, haben Sie wahrscheinlich bereits alle diese Dinge erledigt.  Wenn nicht, gehen Sie wie hier vor:

1. Legen Sie Intune MDM (Verwaltung mobiler Geräte) als Autorität ein.  Wenn Sie Intune noch nie zuvor verwendet haben, müssen Sie die MDM-Autorität festlegen, bevor Sie Geräte registrieren können. Weitere Informationen finden Sie unter ["Festlegen der Verwaltungsbehörde für mobile Geräte".](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)  Dies ist ein einmal durchgeführter Schritt, der beim Erstellen eines neuen Intune-Mandanten durchgeführt werden muss.
2. Aktivieren Sie die Registrierung des Android-Geräteadministrators. Android-basierte Teams-Geräte werden mit Intune als Geräteadministratorgeräte verwaltet.  Die Registrierung von Geräteadministratoren ist für neu erstellte Mandanten standardmäßig deaktiviert.  Weitere Informationen finden Sie unter Registrierung von [Android-Geräteadministratoren.](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)
3. Weisen Sie Benutzern Lizenzen zu. Benutzern von Bei Intune registrierten Teams-Geräten muss eine gültige Lizenz für Intune zugewiesen sein. Weitere Informationen finden Sie unter ["Zuweisen von Lizenzen zu Benutzern, damit sie Geräte in Intune registrieren können".](https://docs.microsoft.com/intune/fundamentals/licenses-assign)
4. Zuweisen von Compliancerichtlinien für Geräteadministratoren.  Erstellen Sie eine Android-Geräteadministrator-Compliancerichtlinie, und weisen Sie sie der Azure Active Directory-Gruppe zu, die die Benutzer enthält, die sich bei den Teams-Geräten anmelden. Weitere Informationen finden Sie unter "Verwenden von Compliancerichtlinien zum Festlegen von Regeln für [Geräte, die Sie mit Intune verwalten".](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)

## <a name="see-also"></a>Siehe auch

[Telefone für Teams](phones-for-teams.md)

[Für Microsoft Teams zertifizierte IP Phones](teams-ip-phones.md)

[Teams wird angezeigt](teams-displays.md)

[Verwalten Ihrer Geräte in Teams](device-management.md).

[Teams Marketplace](https://office.com/teamsdevices)
