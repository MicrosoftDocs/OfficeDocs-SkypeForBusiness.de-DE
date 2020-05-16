---
title: Ressourcenspezifische Zustimmung in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informieren Sie sich über die Einstellungen, die Sie konfigurieren müssen, um zu steuern, ob die Teambesitzer in Ihrer Organisation apps zustimmen können.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54a0565f5126c899ed5fbf9527aa30f83c3bee3b
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256579"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Ressourcenspezifische Zustimmung in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Die ressourcenspezifische Zustimmung in Microsoft Teams ermöglicht es den Teambesitzern, Apps für den Zugriff auf Team Daten zu genehmigen. Beispiele für diesen Zugriff sind die Möglichkeit, Kanal Nachrichten zu lesen, Kanäle zu erstellen und zu löschen sowie Kanal Registerkarten zu erstellen und zu entfernen.

Als Administrator steuern Sie, ob die Teambesitzer in Ihrer Organisation mithilfe des Azure Active Directory (Azure AD) PowerShell-Moduls oder des Azure-Portals und des Microsoft Teams admin Centers die Zustimmung über Einstellungen erteilen können, die Sie konfigurieren.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Festlegen, ob Teambesitzer die Zustimmung zu apps erteilen können

Hier sind die Einstellungen, die Sie festlegen müssen, um zu steuern, ob Teambesitzer die Zustimmung zu Apps geben können. Achten Sie darauf, alle folgenden Einstellungen zu überprüfen.

### <a name="settings-in-azure-ad"></a>Einstellungen in Azure AD

Die beiden folgenden Einstellungen bestimmen, ob Teambesitzer die Zustimmung zu Apps geben können.

> [!IMPORTANT]
> Das Ändern dieser Einstellungen hat keinen Einfluss auf den Datenzugriff für apps, denen bereits eine Genehmigung erteilt wurde. Wenn Sie beispielsweise diese Einstellungen so konfigurieren, dass die Zustimmung der Teambesitzer verhindert wird, entfernen diese Änderungen nicht den bereits gewährten Datenzugriff.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>"Benutzer können den apps zustimmen, die in Ihrem Auftrag auf Unternehmensdaten zugreifen"

Mit dieser Einstellung wird gesteuert, ob Benutzer in Ihrer Organisation apps in Ihrem Auftrag zustimmen können. Damit Teambesitzer die Zustimmung erteilen können, muss diese Einstellung auf **Ja**festgelegt sein. Gehen Sie wie folgt vor, um diese Einstellung zu verwalten:

1. Wechseln Sie im Azure-Portal zu Benutzereinstellungen für **Enterprise-Anwendungen**  >  **User settings**.
2. Unter **Unternehmensanwendungen**können Benutzer festzulegen, **dass apps den Zugriff auf Unternehmensdaten in Ihrem Namen** auf **Nein** oder **Ja**genehmigen.

Sie können diese Einstellung auch mithilfe von PowerShell verwalten. Weitere Informationen finden Sie unter [Konfigurieren von Benutzerinhalten für Anwendungen](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).

#### <a name="the-enablegroupspecificconsent-setting"></a>Die Einstellung "EnableGroupSpecificConsent"

Mit dieser Einstellung wird gesteuert, ob die Benutzer in Ihrer Organisation den apps den Zugriff auf Unternehmensdaten für Ihre eigenen Gruppen zustimmen können. Diese Einstellung muss aktiviert sein, damit die Teambesitzer die Zustimmung erteilen können. Eine schrittweise Anleitung zum Verwalten dieser Einstellung mithilfe von PowerShell finden Sie unter [Konfigurieren der Zustimmung des Gruppen Besitzers zu apps, die auf Gruppendaten zugreifen](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Einstellungen im Microsoft Teams Admin Center

Zusätzlich zu den Einstellungen in Azure AD [-, org-Wide-App-Einstellungen](manage-apps.md#manage-org-wide-app-settings) auf der Seite " [apps verwalten](manage-apps.md) ", unabhängig davon, ob eine APP auf der Seite " [apps verwalten](manage-apps.md#allow-and-block-apps) " blockiert oder zulässig ist, und die dem Teambesitzer zugewiesene [App-Berechtigungsrichtlinie](teams-app-permission-policies.md) bestimmt, ob ein Teambesitzer die Zustimmung erteilen kann.

> [!IMPORTANT]
> Das Ändern dieser Einstellungen hat keinen Einfluss auf den Datenzugriff für apps, denen bereits eine Genehmigung erteilt wurde. Wenn Sie beispielsweise apps von Drittanbietern in der gesamten Organisation deaktivieren oder bestimmte apps blockieren, um zu verhindern, dass Teambesitzer Ihre Zustimmung erteilen, entfernen diese Änderungen den bereits gewährten Datenzugriff nicht.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>Die Einstellung "Drittanbieter-apps zulassen" in den organisationsweiten App-Einstellungen

Diese organisationsweite app-Einstellung steuert, ob Benutzer in Ihrer Organisation Drittanbieter-Apps verwenden können. Diese Einstellung muss aktiviert sein, damit die Teambesitzer die Zustimmung erteilen können. Gehen Sie wie folgt vor, um diese Einstellung zu verwalten:

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**  >  **Verwalten von apps**, und klicken Sie dann auf **organisationsweite App-Einstellungen**.
2. Deaktivieren oder aktivieren Sie unter **apps von Drittanbietern**das **Zulassen von Drittanbieter-apps**.

    ![Screenshot der Einstellung "Drittanbieter-apps in Teams zulassen"](media/resource-specific-consent-org-wide-setting.png)

Sie müssen ggf. bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Zulassen oder Blockieren der APP auf Organisationsebene

Wenn Sie eine APP auf der Seite " [apps verwalten](manage-apps.md#allow-and-block-apps) " blockieren oder zulassen, wird diese APP für alle Benutzer in Ihrer Organisation blockiert oder zugelassen. Team Besitzer können einer APP nur zustimmen, wenn die APP zulässig ist. Gehen Sie wie folgt vor, um eine APP auf Organisationsebene zuzulassen oder zu blockieren:

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**  >  **Verwalten von apps**.
2. Wählen Sie auf der Seite apps verwalten die APP aus, und klicken Sie dann auf **blockieren** , um Sie zu blockieren, oder auf **zulassen** , um Sie zu erlauben.

    ![Screenshot der blockierten apps in organisationsweiten Einstellungen](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Dem Teambesitzer zugewiesene App-Berechtigungsrichtlinie

Team Besitzer können Apps nur zustimmen, wenn Sie von der APP-Berechtigungsrichtlinie ausgeführt werden können. Gehen Sie wie folgt vor, um die APP-Berechtigungsrichtlinie anzuzeigen und zu verwalten, die einem Teambesitzer zugewiesen ist:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**.
2. Doppelklicken Sie auf den Anzeigenamen des Team Besitzers, und klicken Sie dann auf **Richtlinien**.
3. Die dem Teambesitzer zugewiesene Richtlinie wird unter **App-Berechtigungsrichtlinie**aufgeführt.
    - Wenn Sie eine andere Richtlinie zuweisen möchten, klicken Sie auf **Bearbeiten**, und wählen Sie dann die Richtlinie aus, die Sie zuweisen möchten.
    - Wenn Sie die Einstellungen der Richtlinie bearbeiten möchten, die dem Teambesitzer zugewiesen ist, klicken Sie auf den Richtliniennamen, und nehmen Sie dann die gewünschten Änderungen vor.  

## <a name="uploading-custom-apps"></a>Hochladen benutzerdefinierter apps

Wenn Sie eine benutzerdefinierte app (auch bekannt Sideloading) hochladen, die eine ressourcenspezifische Zustimmung verwendet, muss die APP von dem Mandanten stammen, in dem Sie installiert ist. Anders ausgedrückt, muss die Azure AD-App-Registrierung von diesem Mandanten sein. Globale Administratoren sind von dieser Einschränkung ausgenommen und können benutzerdefinierte apps von einem beliebigen Mandanten hochladen, entweder direkt in ein Team (Sideloading) oder in den Mandanten-App-Katalog.

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
