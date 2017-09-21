---
title: Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams | Microsoft-Support
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: overview
ms.service: msteams
description: "Erfahren Sie, wie SharePoint Online und OneDrive for Business mit Microsoft Teams interagieren. Dies beinhaltet Informationen darüber, wie private Chatdateien gespeichert werden sowie die Beziehung zwischen Teams, Kanälen und der Dokumentbibliothek."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: cc4d4f2bd367cce7b3d25d90fdf871e7f1d6982b
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2017
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams
=============================================================================

Jedes Team in Microsoft Teams verfügt über eine Teamsite in SharePoint Online, und jeder Kanal in einem Team erhält einen Ordner innerhalb der Dokumentbibliothek der Standardteamsite. In einer Unterhaltung freigegebene Dateien werden automatisch zur Dokumentbibliothek hinzugefügt, und in SharePoint festgelegte Berechtigungen und Dateisicherheitsoptionen werden automatisch in Teams übernommen.

Private Chatdateien werden im OneDrive-Ordner des **Absenders** gespeichert, und Berechtigungen werden automatisch allen Teilnehmern als Teil des Dateifreigabevorgangs zugewiesen.

Wenn in Ihrem Mandanten SharePoint Online nicht aktiviert ist, können Microsoft Teams-Benutzer nicht immer Dateien in Teams freigeben. Benutzer in privaten Chats können ebenfalls keine Dateien freigeben, weil OneDrive for Business (an die SharePoint-Lizenz gebunden) für diese Funktionalität erforderlich ist.

Beim Speichern der Dateien in der SharePoint Online-Dokumentbibliothek und OneDrive for Business werden alle auf der Mandantenebene konfigurierten Complianceregeln eingehalten.

Im Folgenden finden Sie ein Beispiel für die Beziehungen zwischen Team, Kanal und Dokumentbibliothek.

Für jedes Team wird eine SharePoint-Site erstellt, und der Ordner*Freigegebene Dokumente* ist der für das Team erstellte Standardordner. Für jeden Kanal, einschließlich des Kanals **Allgemein** beinhaltet der Standardkanal für jedes Team einen Ordner unter *Freigegebene Dokumente*.

![](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

Für jeden Benutzer wird der OneDrive-Ordner *Microsoft Teams-Chatdateien* zum Speichern aller innerhalb der in privaten Chats für andere Benutzer (1:1 oder 1:viele) freigegebenen Dateien mit automatisch konfigurierten Berechtigungen verwendet, um den Zugriff auf den gewünschten Benutzer zu beschränken.

![](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
