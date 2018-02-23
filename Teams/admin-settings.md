---
title: "Administratoreinstellungen für Apps in Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 01/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: "Hier erfahren Sie, wie Apps in Microsoft Teams aktiviert werden. Dazu zählt auch das Querladen von externen Apps."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4cdca98cca13ffb49575b808a5cfa82f784d1752
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Administratoreinstellungen für Apps in Microsoft Teams
==========================================

Apps sind Registerkarten, Connectors und Bots bzw. eine beliebige Kombination dieser drei Elemente, die von einem Drittanbieterdienst bereitgestellt werden. Im Office 365 Admin Center können Microsoft Teams-Administratorrichtlinien konfiguriert werden, um zu steuern, welche externen Drittanbieter-Apps zulässig sind. Mit diesen Richtlinien können Sie festlegen, welche Apps zulässig bzw. nicht zulässig sind, das Verhalten neuer externer Apps definieren und angeben, ob das Querladen von Apps zulässig ist.

> [!NOTE]
> Um die Administratoreinstellungen für Apps in Microsoft Teams zu verwalten, wechseln Sie zum Office 365 Admin Center. Öffnen Sie **Einstellungen** > **Dienste und Add-Ins**, und wählen Sie dann **Microsoft Teams** aus. Wenn Sie als Office 365-Administrator angemeldet sind, können Sie diesen Link verwenden:
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

## <a name="allow-external-apps-in-teams"></a>Zulassen von externen Apps in Microsoft Teams

Standardmäßig ist die Option **Allow external apps in Microsoft Teams** (Externe Apps in Microsoft Teams zulassen) aktiviert, und alle Apps sind ausgewählt.  Wenn Sie diese Option deaktivieren, sind alle externen Drittanbieter-Apps deaktiviert. 

## <a name="enable-new-external-apps-by-default"></a>Standardmäßiges Aktivieren von neuen externen Apps

#### <a name="trophy-best-practice-manage-external-apps-individually"></a>:trophy: Bewährte Methode: Verwalten Sie externe Apps einzeln. 
 
Um einige Apps zu aktivieren (und andere zu deaktivieren), deaktivieren Sie **Allow sideloading of external apps** (Querladen von externen Apps zulassen). Deaktivieren Sie dann die Apps, die Ihre Benutzer nicht verwenden sollen. Optional: Deaktivieren Sie **Enable new external apps by default** (Neue externe Apps standardmäßig aktivieren), wenn Sie neue Apps steuern möchten. 

Wenn diese Option aktiviert ist, können Benutzer neue Apps aktivieren, sobald diese zum Microsoft Teams-App-Katalog hinzugefügt werden. Um den Microsoft Teams-App-Katalog zu öffnen, klicken Sie unten in Microsoft Teams auf **Store** und dann auf **Apps**. Wenn Sie die Verfügbarkeit von Apps steuern möchten, deaktivieren Sie diese Option. Wenn Sie die Option deaktiviert haben, müssen Sie natürlich daran denken, neue Apps regelmäßig zu überprüfen, damit Ihrer Organisation keine tollen neuen Apps entgehen. 

Querladen ist das Verfahren zum Hinzufügen einer App in Microsoft Teams, indem Sie eine ZIP-Datei direkt in ein Team hochladen. Mithilfe von Querladen können Sie Apps schon während der Entwicklung testen. Außerdem können Sie eine App nur zur internen Verwendung erstellen und für Ihr Team freigeben, ohne sie an den Microsoft Teams-App-Katalog im Office Store zu übermitteln. 

Nur Teambesitzer oder Mitglieder mit den entsprechenden Berechtigungen können Apps in Microsoft Teams querladen.  

![Screenshot des Abschnitts „Apps“ in den Microsoft Teams-Einstellungen](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png) 

## <a name="creating-and-uploading-app-packages"></a>Erstellen und Hochladen von App-Paketen 

Weitere Informationen zu Apps finden Sie unter [Apps für Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview). 



