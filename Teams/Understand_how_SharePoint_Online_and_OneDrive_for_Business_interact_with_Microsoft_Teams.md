---
title: Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams | Microsoft-Support
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/10/2017
ms.topic: overview
ms.prod: teams
description: "Erfahren Sie, wie SharePoint Online und OneDrive for Business mit Microsoft Teams interagieren. Dies beinhaltet Informationen darüber, wie private Chatdateien gespeichert werden sowie die Beziehung zwischen Teams, Kanälen und der Dokumentbibliothek."
ms.openlocfilehash: e43bd32cb7f999ff5de60b711f04a9eb079cd17c
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2017
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="6ff2f-103">Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6ff2f-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>
=============================================================================

<span data-ttu-id="6ff2f-p101">Jedes Team in Microsoft Teams verfügt über eine Teamsite in SharePoint Online, und jeder Kanal in einem Team erhält einen Ordner innerhalb der Dokumentbibliothek der Standardteamsite. In einer Unterhaltung freigegebene Dateien werden automatisch zur Dokumentbibliothek hinzugefügt, und in SharePoint festgelegte Berechtigungen und Dateisicherheitsoptionen werden automatisch in Teams übernommen.</span><span class="sxs-lookup"><span data-stu-id="6ff2f-p101">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="6ff2f-106">Private Chatdateien werden im OneDrive-Ordner des **Absenders** gespeichert, und Berechtigungen werden automatisch allen Teilnehmern als Teil des Dateifreigabevorgangs zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6ff2f-106">Private chat files are stored in the **sender’s** OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="6ff2f-p102">Wenn in Ihrem Mandanten SharePoint Online nicht aktiviert ist, können Microsoft Teams-Benutzer nicht immer Dateien in Teams freigeben. Benutzer in privaten Chats können ebenfalls keine Dateien freigeben, weil OneDrive for Business (an die SharePoint-Lizenz gebunden) für diese Funktionalität erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="6ff2f-p102">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams’ users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="6ff2f-109">Beim Speichern der Dateien in der SharePoint Online-Dokumentbibliothek und OneDrive for Business werden alle auf der Mandantenebene konfigurierten Complianceregeln eingehalten.</span><span class="sxs-lookup"><span data-stu-id="6ff2f-109">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span>

<span data-ttu-id="6ff2f-110">Im Folgenden finden Sie ein Beispiel für die Beziehungen zwischen Team, Kanal und Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="6ff2f-110">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="6ff2f-p103">Für jedes Team wird eine SharePoint-Site erstellt, und der Ordner*Freigegebene Dokumente* ist der für das Team erstellte Standardordner. Für jeden Kanal, einschließlich des Kanals **Allgemein** beinhaltet der Standardkanal für jedes Team einen Ordner unter *Freigegebene Dokumente*.</span><span class="sxs-lookup"><span data-stu-id="6ff2f-p103">For every team, a SharePoint site is created, and the *Shared Documents* folder is the default folder created for the team. Each channel, including the **General** channel, the default channel for each team, has a folder under the *Shared Documents* folder.</span></span>

![](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

<span data-ttu-id="6ff2f-113">Für jeden Benutzer wird der OneDrive-Ordner *Microsoft Teams-Chatdateien* zum Speichern aller innerhalb der in privaten Chats für andere Benutzer (1:1 oder 1:viele) freigegebenen Dateien mit automatisch konfigurierten Berechtigungen verwendet, um den Zugriff auf den gewünschten Benutzer zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="6ff2f-113">For every user, the OneDrive folder *Microsoft Teams Chat Files* is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
