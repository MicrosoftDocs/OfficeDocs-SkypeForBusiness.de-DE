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
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: da73768f69159c32543d0843139facc2b9ef4f9a
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2019
ms.locfileid: "29706355"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Administratoreinstellungen für Apps in Microsoft Teams
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Apps werden Registerkarten, Connectors, Bots oder eine beliebige Kombination der folgenden drei, von Teams (erste Teilnehmern apps und auch bekannt als Standard-apps) oder einem Drittanbieter (auch als externe apps bezeichnet) bereitgestellt. In der Microsoft-365-Verwaltungskonsole können Sie aktivieren und Deaktivieren von Standard-apps und Konfigurieren von Einstellungen, um externe apps zu steuern. Diese Einstellungen können Sie angeben, welche externen apps zulässig sind und nicht zulässig, neue externe app Verhalten und ob Seite laden apps zulässig ist.

 Zum Verwalten von Einstellungen für apps in Teams Admin, wechseln Sie zur Microsoft 365 Administrationscenter, und wählen Sie **Einstellungen** > **Services &-add-ins** > **Microsoft-Teams**. Wenn Sie als Office 365-Administrator angemeldet sind, können Sie diesen Link verwenden:

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

Weitere Informationen zu Administratoreinstellungen für Apps erhalten Sie im folgenden Video: 
 
|  |  |
|---------|---------|
| Verwalten der App-Funktionen in Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a>Zulassen von externen Apps in Microsoft Teams

Standardmäßig ist die Option **Allow external apps in Microsoft Teams** (Externe Apps in Microsoft Teams zulassen) aktiviert, und alle Apps sind ausgewählt.  Wenn Sie diese Einstellung deaktivieren, werden alle externen Drittanbieter-apps deaktiviert. 

## <a name="enable-new-external-apps-by-default"></a>Standardmäßiges Aktivieren von neuen externen Apps

#### <a name="trophy-best-practice-manage-external-apps-individually"></a>:trophy: Bewährte Methode: Verwalten Sie externe Apps einzeln. 
 
Um einige Apps zu aktivieren (und andere zu deaktivieren), deaktivieren Sie **Allow sideloading of external apps** (Querladen von externen Apps zulassen). Deaktivieren Sie dann die Apps, die Ihre Benutzer nicht verwenden sollen. Optional: Deaktivieren Sie **Enable new external apps by default** (Neue externe Apps standardmäßig aktivieren), wenn Sie neue Apps steuern möchten. 

> [!NOTE]
> Standard-apps beispielsweise derjenigen, die von Microsoft, sind von der Einstellung der **Aktivieren von neuen externen apps standardmäßig** nicht betroffen. Neue apps sind bei Microsoft veröffentlicht standardmäßig aktiviert.

Wenn diese Einstellung aktiviert ist, können Benutzer neue apps aktivieren, sobald zum Teams app-Katalog aufgenommen. Um den Microsoft Teams-App-Katalog zu öffnen, klicken Sie unten in Microsoft Teams auf **Store** und dann auf **Apps**. Wenn Sie möchten steuern, welche apps verfügbar sind, deaktivieren Sie diese Einstellung. Wenn Sie die Option deaktiviert haben, müssen Sie natürlich daran denken, neue Apps regelmäßig zu überprüfen, damit Ihrer Organisation keine tollen neuen Apps entgehen. 

Querladen ist das Verfahren zum Hinzufügen einer App in Microsoft Teams, indem Sie eine ZIP-Datei direkt in ein Team hochladen. Mithilfe von Querladen können Sie Apps schon während der Entwicklung testen. Außerdem können Sie eine App nur zur internen Verwendung erstellen und für Ihr Team freigeben, ohne sie an den Microsoft Teams-App-Katalog im Office Store zu übermitteln. 

Nur Teambesitzer oder Mitglieder mit den entsprechenden Berechtigungen können Apps in Microsoft Teams querladen.  

![Screenshot des Abschnitts erweiterte externe Apps.] (media/teams-tenant-wide-settings-external-apps.png "Screenshot des erweiterten externe Apps Abschnitts mit externen apps")

## <a name="creating-and-uploading-app-packages"></a>Erstellen und Hochladen von App-Paketen 

Weitere Informationen zu apps finden Sie unter [Entwickeln von apps für Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview). 



