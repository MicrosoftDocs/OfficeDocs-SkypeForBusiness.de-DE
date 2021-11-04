---
title: Bereitstellen Teams Smartphones, Teams Anzeigen und Microsoft Teams-Räume unter Android mithilfe von Intune
ms.author: v-mahoffman
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
ms.localizationpriority: medium
description: Dieser Artikel bietet eine Übersicht über die von der Anzeige Microsoft Teams Features.
ms.openlocfilehash: 3d89dce290d241eebd3d71da560bb383a81f6a2a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746471"
---
# <a name="deploy-teams-phones-teams-displays-and-microsoft-teams-rooms-on-android-using-intune"></a>Bereitstellen Teams Smartphones, Teams Anzeigen und Microsoft Teams-Räume unter Android mithilfe von Intune

Dieser Artikel gibt Ihnen einen Überblick über das Bereitstellen von Teams Smartphones, Teams Anzeigen und Microsoft Teams-Räume mit Intune unter Android.

## <a name="conditional-access"></a>Bedingter Zugriff

Der bedingte Zugriff ist ein Azure Active Directory(Azure AD)-Feature, mit dem Sie sicherstellen können, dass Geräte, auf die auf Ihre Office 365-Ressourcen zugreifen, ordnungsgemäß verwaltet und sicher sind.  Wenn Sie Richtlinien für bedingten Zugriff auf den Teams-Dienst anwenden, müssen Android-Geräte (einschließlich Teams-Smartphones, Teams-Displays und Microsoft Teams-Räume unter Android), die auf Teams zugreifen, bei Intune registriert sein, und deren Einstellungen müssen Ihren Richtlinien entsprechen.  Wenn das Gerät nicht bei Intune registriert ist oder wenn es registriert ist, seine Einstellungen aber nicht Ihren Richtlinien entsprechen, verhindert bedingter Zugriff, dass sich ein Benutzer auf dem Gerät bei der Teams-App anmelden oder diese verwenden kann.

In der Regel werden in Intune definierte Compliancerichtlinien Benutzergruppen zugewiesen.  Dies bedeutet: Wenn Sie user@contoso.com eine Android-Compliancerichtlinie zuweisen, gilt diese Richtlinie gleichermaßen für das Android-Smartphone und jedes Android-basierte Teams-Gerät, bei dem user@contoso.com ist.

Wenn Sie den bedingten Zugriff verwenden, für den die Intune-Registrierung erzwungen werden muss, müssen Sie in Ihrer Organisation ein paar Dinge einrichten, die Sie einrichten müssen, um eine erfolgreiche Intune-Registrierung zu ermöglichen:

- **Intune-Lizenz** Der Benutzer, der sich beim Teams angemeldet hat, muss für Intune lizenziert sein.  Solange das Teams-Gerät bei einem Benutzerkonto angemeldet ist, das über eine gültige Intune-Lizenz verfügt, wird das Gerät im Rahmen des Anmeldevorgangs automatisch in Microsoft Intune registriert.
- **Konfigurieren von Intune** Sie müssen einen ordnungsgemäß konfigurierten Intune-Mandanten für die Registrierung durch den Android-Geräteadministrator eingerichtet haben.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Konfigurieren von Intune für die Teams von Android-basierten Geräten

Teams Android-basierte Geräte werden von Intune über die Verwaltung durch den Android-Geräteadministrator (Da) verwaltet. Bevor Geräte bei Intune registriert werden können, müssen Sie ein paar grundlegende Schritte ausführen.  Wenn Sie Geräte bereits heute mit Intune verwalten, haben Sie wahrscheinlich bereits all diese Dinge erledigt.  Wenn nicht, gehen Sie wie hier gezeigt vor:

> [!NOTE]
> - Wenn Mandantenadministratoren allgemeine Telefone in Intune registrieren möchten, müssen sie dem Konto eine Intune-Lizenz hinzufügen und die Schritte für die Intune-Registrierung ausführen.
> - Wenn das Benutzerkonto, das zum Anmelden bei einem Teams-Gerät verwendet wurde, nicht für Intune lizenziert ist, müssen Intune-Compliancerichtlinien und Registrierungseinschränkungen für das Konto deaktiviert werden.



1. Legen Sie Intune MDM -Autorität (Verwaltung mobiler Geräte) festgelegt.  

   Wenn Sie Intune noch nie zuvor verwendet haben, müssen Sie die MDM-Autorität festlegen, bevor Sie Geräte registrieren können. Weitere Informationen finden Sie unter [Festlegen der Verwaltungsbehörde für mobile Geräte.](/intune/fundamentals/mdm-authority-set)  Dies ist ein einmal zu erledigener Schritt beim Erstellen eines neuen Intune-Mandanten.
1. Aktivieren Sie die Registrierung des Android-Geräteadministrators.
  
   Android-basierte Teams Geräte werden mit Intune als Geräteadministratorgeräte verwaltet.  Die Geräteadministratorregistrierung ist für neu erstellte Mandanten standardmäßig deaktiviert. Weitere Informationen [finden Sie unter Registrierung des Android-Geräteadministrators.](/intune/enrollment/android-enroll-device-administrator)
1. Zuweisen von Lizenzen zu Benutzern 
 
   Benutzern von Teams, die sich bei Intune registrieren, muss eine gültige Intune-Lizenz zugewiesen sein. Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzern, damit diese Geräte in Intune registrieren können.](/intune/fundamentals/licenses-assign)
1. Zuweisen von Compliancerichtlinien für Geräteadministratoren  

   1. Erstellen Sie eine Compliancerichtlinie für den Android-Geräteadministrator.

   1. Weisen Sie sie der gruppe Azure Active Directory zu, die die Benutzer enthält, die sich bei den Teams anmelden. Weitere Informationen finden Sie unter Verwenden von [Compliancerichtlinien zum Festlegen von Regeln für Geräte, die Sie mit Intune verwalten.](/mem/intune/protect/device-compliance-get-started)

## <a name="see-also"></a>Mehr dazu

[Telefone für Teams](phones-for-teams.md)

[Ip Phones certified for Microsoft Teams](teams-ip-phones.md)

[Teams anzeigen](teams-displays.md)

[Verwalten Ihrer Geräte in Teams](device-management.md).

[Teams Marketplace](https://office.com/teamsdevices)
