---
title: AppLocker-Anwendungssteuerungsrichtlinien in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Desktopclientanwendung für Teams mit AppLocker-Anwendungssteuerungsrichtlinien aktivieren.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6035341aa649e966f15be7d33894f450ec8be251
ms.sourcegitcommit: b1bf37a96a8faa169d8a32b7478f1e2d1022ebbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311250"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="3caed-103">AppLocker-Anwendungssteuerungsrichtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3caed-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="3caed-104">In diesem Artikel wird erläutert, wie Sie die Desktop Client-App für Teams mit AppLocker-Anwendungssteuerungsrichtlinien aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3caed-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="3caed-105">Die Verwendung von AppLocker dient dazu, die Programm-und Skriptausführung durch nicht administrative Benutzer zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="3caed-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="3caed-106">Weitere Informationen und Anleitungen zu AppLocker finden Sie unter [Was ist AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span><span class="sxs-lookup"><span data-stu-id="3caed-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="3caed-107">Das Verfahren zum Aktivieren von Teams mit AppLocker erfordert das Erstellen von AppLocker-basierten Whitelisting-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="3caed-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based whitelisting policies.</span></span> <span data-ttu-id="3caed-108">Richtlinien werden mit der Gruppenrichtlinien-Verwaltungssoftware und/oder der Verwendung von Windows PowerShell-Cmdlets für AppLocker erstellt (Weitere Informationen finden Sie in der [technischen Referenz zu AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) ).</span><span class="sxs-lookup"><span data-stu-id="3caed-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="3caed-109">Die AppLocker-Richtlinie wird im XML-Format gespeichert und kann mit einem beliebigen Text-oder XML-Editor bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3caed-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-whitelisting-with-applocker"></a><span data-ttu-id="3caed-110">Whitelists von Teams mit AppLocker</span><span class="sxs-lookup"><span data-stu-id="3caed-110">Teams whitelisting with AppLocker</span></span>

<span data-ttu-id="3caed-111">AppLocker-Regeln sind in Regelsammlungen unterteilt.</span><span class="sxs-lookup"><span data-stu-id="3caed-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="3caed-112">AppLocker-Regeln gelten für die Ziel-APP und sind die Komponenten, aus denen die AppLocker-Richtlinie besteht.</span><span class="sxs-lookup"><span data-stu-id="3caed-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="3caed-113">Für die Whitelist von Teams empfehlen wir die Verwendung der [Herausgeber Konditions Regeln](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) , da alle Teams-APP-Dateien digital signiert sind.</span><span class="sxs-lookup"><span data-stu-id="3caed-113">To whitelist Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="3caed-114">Es wird nicht empfohlen, Pfadregeln zu verwenden, da das Installationsverzeichnis für Teams vom Benutzer beschreibbar ist.</span><span class="sxs-lookup"><span data-stu-id="3caed-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="3caed-115">Wir empfehlen auch nicht die Verwendung von Hashregeln, da die Regeln jedes Mal aktualisiert werden müssen, wenn die Client-App für Teams aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="3caed-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="3caed-116">Da die ausführbaren Dateien des Teams-Desktops digital signiert sind, identifiziert die Publisher-Bedingung eine APP-Datei auf der Grundlage ihrer digitalen Signatur und der eingebetteten Versionsattribute.</span><span class="sxs-lookup"><span data-stu-id="3caed-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="3caed-117">Die digitale Signatur enthält Informationen über das Unternehmen, das die APP-Datei (den Herausgeber) erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="3caed-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="3caed-118">Die Versionsinformationen, die aus der binären Ressource abgerufen werden, enthalten den Namen des Produkts, zu dem die Datei gehört, und die Versionsnummer der Anwendungsdatei.</span><span class="sxs-lookup"><span data-stu-id="3caed-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="3caed-119">Beispiel für Herausgeber Konditions Regeln</span><span class="sxs-lookup"><span data-stu-id="3caed-119">Example of publisher condition rules</span></span>

<span data-ttu-id="3caed-120">Für die Client-App "Teams" (alle Dateien, alle Versionen) fügen Sie den ausführbaren Regeln #a0 dll-Regeln Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="3caed-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="3caed-121">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3caed-121">Related topics</span></span>
<span data-ttu-id="3caed-122">[Was ist AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Technische Referenz zu AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="3caed-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>
