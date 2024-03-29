---
title: Verwalten von Ressourcenkonten in Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie Ressourcenkonten in Microsoft Teams erstellen, bearbeiten und verwalten.
ms.openlocfilehash: 0b8c77f7d6371ba1bfefa9837488415405e48f67
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615801"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Verwalten von Ressourcenkonten in Microsoft Teams

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die Einrichtung des Ressourcenkontos abgeschlossen und bei Bedarf eine Dienstnummer zugewiesen haben, können Sie das Ressourcenkonto mit einer automatischen Telefonzentrale oder Anrufwarteschleife verwenden.

Weitere Informationen finden Sie in den folgenden Verweisen:

- [Automatische Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md)
- [Cloud-Anrufwarteschleife](create-a-phone-system-call-queue.md)

Sie können den **Anzeigenamen** des Ressourcenkontos und den **Ressourcenkontotyp** mithilfe der Option **"Bearbeiten"** bearbeiten. Klicken Sie abschließend auf **Speichern**.

## <a name="change-an-existing-resource-account-to-use-a-teams-phone-resource-account-license"></a>Ändern eines vorhandenen Ressourcenkontos zur Verwendung einer Teams Phone-Ressourcenkontolizenz

Wenn Sie die Lizenzen für Ihr vorhandenes Ressourcenkonto von einer **Teams Telefon Standard-Lizenz** auf eine **Microsoft Teams Telefon Ressourcenkontolizenz** umstellen möchten, müssen Sie die kostenlose **Microsoft Teams Phone-Ressourcenkontolizenz** erwerben und dann die Schritte in der Microsoft 365 Admin Center, [um Benutzer in ein anderes Abonnement zu verschieben](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Entfernen Sie immer eine vollständige Teams Telefon Standard-Lizenz, und weisen Sie die **Microsoft Teams Telefon Resource Account-Lizenz** in derselben Lizenzaktivität zu. Wenn Sie die alte Lizenz entfernen, die Kontoänderungen speichern, die neue Lizenz hinzufügen und dann die Kontoeinstellungen erneut speichern, funktioniert das Ressourcenkonto möglicherweise nicht mehr wie erwartet. In diesem Fall wird empfohlen, ein neues Ressourcenkonto für die **Lizenz Microsoft Teams Telefon Ressourcenkonto** zu erstellen und das fehlerhafte Ressourcenkonto zu entfernen.

## <a name="skype-for-business-server-2019"></a>Skype for Business Server 2019

Informationen zu Ressourcenkonten, die in Skype for Business Server 2019 verwaltet werden und mit Cloudanrufwarteschleifen und automatischen Cloudtelefonzentralen verwendet werden können, finden Sie unter [Planen von Cloud-Anrufwarteschleifen](/SkypeforBusiness/hybrid/plan-call-queue) oder ["Planen automatischer Cloudtelefonzentralen](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)". Hybridimplementierungen (Nummern, die auf Direct Routing verwaltet werden) werden mithilfe des Cmdlets ["New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint)" auf einem lokalen Skype for Business Server 2019-Server konfiguriert.

Die Anwendungs-IDs, die Sie beim Erstellen der Anwendungsinstanzen verwenden müssen, sind:

- **Automatische Telefonzentrale:** ce933385-9390-45d1-9512-c8d228074e07
- **Anrufwarteschleife:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Wenn Sie möchten, dass die Anrufwarteschleife oder automatische Telefonzentrale von Benutzern von Skype For Business Server 2019 durchsucht werden kann, sollten Sie Ihre Ressourcenkonten in Skype For Business Server 2019 erstellen, da Online-Ressourcenkonten nicht mit Active Directory synchronisiert werden. Wenn DNS SRV-Einträge für sipfederationtls in Skype for Business Server 2019 aufgelöst werden, **müssen** Ressourcenkonten auf Skype for Business Server 2019 mithilfe der SfB-Verwaltungsshell erstellt und mit Azure AD synchronisiert werden.

Bei hybride Implementierungen mit Skype for Business Server:

   [Planen automatischer Cloudtelefonzentralen](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

   [Planen von Cloud-Anrufwarteschleifen](/SkypeforBusiness/hybrid/plan-call-queue)

   [Konfigurieren lokalen von Ressourcenkonten](/SkypeForBusiness/hybrid/configure-onprem-ra)

## <a name="delete-a-resource-account"></a>Löschen eines Ressourcenkontos

Stellen Sie sicher, dass Sie die Telefonnummer vom Ressourcenkonto trennen, bevor Sie sie löschen, um zu verhindern, dass Ihre Dienstnummer im Modus „Ausstehend“ verbleibt.

Danach können Sie das Ressourcenkonto im Microsoft 365 Admin Center unter der Registerkarte "Benutzer" löschen.

Verwenden Sie den folgenden Cmdlet, um eine direkte Routing-Telefonnummer vom Ressourcenkonto zu trennen:

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```
