---
title: Administratoreinstellungen für Apps in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag
description: Hier erfahren Sie, wie Apps in Microsoft Teams aktiviert werden. Dazu zählt auch das Querladen von externen Apps.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14c4759505b83d0039fabcaa5eeb03b1530ddf1b
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23853143"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Administratoreinstellungen für Apps in Microsoft Teams
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Apps werden Registerkarten, Connectors, Bots oder eine beliebige Kombination der folgenden drei, von einem Drittanbieter-Dienst bereitgestellt. Es gibt Teams Admin Richtlinien, die im Office 365 Administrationscenter auf Steuerelement konfiguriert werden können, welche externen Drittanbieter-apps zulässig sind. Diese Richtlinien können Sie angeben, welche apps zulässig sind und nicht zulässig, neue externe app Verhalten und ob Seite laden apps zulässig ist.

> [!NOTE]
> Um die Administratoreinstellungen für Apps in Microsoft Teams zu verwalten, wechseln Sie zum Office 365 Admin Center. Öffnen Sie **Einstellungen** > **Dienste und Add-Ins**, und wählen Sie dann **Microsoft Teams** aus. Wenn Sie als Office 365-Administrator angemeldet sind, können Sie diesen Link verwenden:
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

Weitere Informationen zu Administratoreinstellungen für Apps erhalten Sie im folgenden Video: 
 
|  |  |
|---------|---------|
| Verwalten der App-Funktionen in Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a>Zulassen von externen Apps in Microsoft Teams

Standardmäßig ist die Option **Allow external apps in Microsoft Teams** (Externe Apps in Microsoft Teams zulassen) aktiviert, und alle Apps sind ausgewählt.  Wenn Sie diese Option deaktivieren, sind alle externen Drittanbieter-Apps deaktiviert. 

## <a name="enable-new-external-apps-by-default"></a>Standardmäßiges Aktivieren von neuen externen Apps

#### <a name="trophy-best-practice-manage-external-apps-individually"></a>:trophy: Bewährte Methode: Verwalten Sie externe Apps einzeln. 
 
Um einige Apps zu aktivieren (und andere zu deaktivieren), deaktivieren Sie **Allow sideloading of external apps** (Querladen von externen Apps zulassen). Deaktivieren Sie dann die Apps, die Ihre Benutzer nicht verwenden sollen. Optional: Deaktivieren Sie **Enable new external apps by default** (Neue externe Apps standardmäßig aktivieren), wenn Sie neue Apps steuern möchten. 

> [!NOTE]
> Standard-apps beispielsweise derjenigen, die von Microsoft, sind von der Einstellung der **Aktivieren von neuen externen apps standardmäßig** nicht betroffen. Neue apps sind bei Microsoft veröffentlicht standardmäßig aktiviert.

Wenn diese Option aktiviert ist, können Benutzer neue Apps aktivieren, sobald diese zum Microsoft Teams-App-Katalog hinzugefügt werden. Um den Microsoft Teams-App-Katalog zu öffnen, klicken Sie unten in Microsoft Teams auf **Store** und dann auf **Apps**. Wenn Sie die Verfügbarkeit von Apps steuern möchten, deaktivieren Sie diese Option. Wenn Sie die Option deaktiviert haben, müssen Sie natürlich daran denken, neue Apps regelmäßig zu überprüfen, damit Ihrer Organisation keine tollen neuen Apps entgehen. 

Querladen ist das Verfahren zum Hinzufügen einer App in Microsoft Teams, indem Sie eine ZIP-Datei direkt in ein Team hochladen. Mithilfe von Querladen können Sie Apps schon während der Entwicklung testen. Außerdem können Sie eine App nur zur internen Verwendung erstellen und für Ihr Team freigeben, ohne sie an den Microsoft Teams-App-Katalog im Office Store zu übermitteln. 

Nur Teambesitzer oder Mitglieder mit den entsprechenden Berechtigungen können Apps in Microsoft Teams querladen.  

![Screenshot des Abschnitts erweiterte Apps in den Mandanten geltende-Einstellungen.](media/Admin_settings_for_apps_in_Microsoft_Teams_image2.png)

## <a name="creating-and-uploading-app-packages"></a>Erstellen und Hochladen von App-Paketen 

Weitere Informationen zu apps finden Sie unter [Entwickeln von apps für Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview). 



