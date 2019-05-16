---
title: Richtlinien für die Kontrolle von AppLocker Anwendung in Microsoft-Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: Erfahren Sie, wie die Teams Desktopclientanwendung mit AppLocker Steuerelement Richtlinien aktivieren.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04379cad0ab224915a02475b010f908d486284cc
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34063210"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="a8d60-103">Richtlinien für die Kontrolle von AppLocker Anwendung in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="a8d60-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="a8d60-104">In diesem Artikel wird erläutert, wie die Teams Desktopclient app mit Richtlinien AppLocker-Steuerelement zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a8d60-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="a8d60-105">Verwendung von AppLocker dient zur Ausführung von Programm- und Skript Einschränken von Benutzern ohne Administratorrechte.</span><span class="sxs-lookup"><span data-stu-id="a8d60-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="a8d60-106">Weitere Informationen und Anleitungen zu AppLocker finden Sie unter [Neuigkeiten AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span><span class="sxs-lookup"><span data-stu-id="a8d60-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="a8d60-107">Das Verfahren zum Aktivieren von Teams mit AppLocker erfordert die Erstellung von AppLocker-basierte mithilfe von Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="a8d60-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based whitelisting policies.</span></span> <span data-ttu-id="a8d60-108">Richtlinien mit Group Policy Managementsoftware und/oder die Verwendung von Windows PowerShell-Cmdlets für AppLocker erstellt werden (siehe die [AppLocker technische Referenz](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) für Weitere Informationen).</span><span class="sxs-lookup"><span data-stu-id="a8d60-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="a8d60-109">Die Richtlinie AppLocker wird im XML-Format gespeichert und kann mit einem Text- oder XML-Editor bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="a8d60-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-whitelisting-with-applocker"></a><span data-ttu-id="a8d60-110">Mithilfe von Teams mit AppLocker</span><span class="sxs-lookup"><span data-stu-id="a8d60-110">Teams whitelisting with AppLocker</span></span>

<span data-ttu-id="a8d60-111">AppLocker-Regeln sind in Sammlungen von Regeln organisiert.</span><span class="sxs-lookup"><span data-stu-id="a8d60-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="a8d60-112">AppLocker-Regeln gelten für die gezielte app, und sie sind die Komponenten, die die Richtlinie AppLocker bilden.</span><span class="sxs-lookup"><span data-stu-id="a8d60-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="a8d60-113">Weiße Teams wird empfohlen, dass Sie die [Publisher Bedingungsregeln](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) verwenden, da alle Teams app Dateien digital signiert werden.</span><span class="sxs-lookup"><span data-stu-id="a8d60-113">To whitelist Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="a8d60-114">Es wird nicht die Verwendung von Pfadregeln empfohlen, da das Installationsverzeichnis Teams Benutzer nicht schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="a8d60-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="a8d60-115">Nicht auch empfohlen die Verwendung von Hashregeln, da die Regeln müssten aktualisiert werden, wenn die Client-Teams app aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="a8d60-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="a8d60-116">Da Teams desktop ausführbare Dateien digital signiert werden, identifiziert die Publisher Bedingung basierte auf der digitalen Signatur und eingebettete Versionsattribute eine app-Datei.</span><span class="sxs-lookup"><span data-stu-id="a8d60-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="a8d60-117">Die digitale Signatur enthält Informationen über das Unternehmen, das die app-Datei (Herausgeber) erstellt.</span><span class="sxs-lookup"><span data-stu-id="a8d60-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="a8d60-118">Die Informationen zur Version, die von der Binärressource abgerufen wird, enthält den Namen des Produkts, die Datei Teil ist, und die Versionsnummer der Datei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a8d60-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="a8d60-119">Beispiel für Publisher Bedingungsregeln</span><span class="sxs-lookup"><span data-stu-id="a8d60-119">Example of publisher condition rules</span></span>

<span data-ttu-id="a8d60-120">Für Teams-Client-Anwendung (alle Dateien, alle Versionen):</span><span class="sxs-lookup"><span data-stu-id="a8d60-120">For the Teams client app (all files, all versions):</span></span>

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a><span data-ttu-id="a8d60-121">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a8d60-121">Related topics</span></span>
<span data-ttu-id="a8d60-122">[Was ist AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [AppLocker technische Referenz](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="a8d60-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>