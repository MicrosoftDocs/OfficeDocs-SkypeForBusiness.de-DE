---
title: Verwenden von Setup-Befehlszeilenoptionen für Skype for Business-Clients
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Zusammenfassung: erfahren Sie mehr über die Befehlszeilenfunktionen von Setup. exe in Office Setup.'
ms.openlocfilehash: 68add6e2744e9648db49508519c14e64b4e6aeef
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768628"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="b0659-103">Verwenden von Setup-Befehlszeilenoptionen für Skype for Business-Clients</span><span class="sxs-lookup"><span data-stu-id="b0659-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="b0659-104">**Zusammenfassung:** Informieren Sie sich über die Befehlszeilenfunktionen von Setup. exe in Office-Setup.</span><span class="sxs-lookup"><span data-stu-id="b0659-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="b0659-105">Die Befehlszeile von "Setup.exe" wird nur für wenige Vorgänge des Office-Setups verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0659-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="b0659-106">Anstatt die Setup-Befehlszeilenoptionen zu verwenden, verwenden Sie in der Regel das Office-Anpassungs Tool und die Datei config. XML für die Produkteinrichtung und die Anpassung von Features.</span><span class="sxs-lookup"><span data-stu-id="b0659-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="b0659-107">Die Befehlszeile der Office "Setup.exe" erkennt die in der folgenden Tabelle beschriebenen Befehlzeilenoptionen.</span><span class="sxs-lookup"><span data-stu-id="b0659-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="b0659-108">**Optionen der Office Setup-Befehlszeile**</span><span class="sxs-lookup"><span data-stu-id="b0659-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="b0659-109">**Option der Office Setup-Befehlszeile**</span><span class="sxs-lookup"><span data-stu-id="b0659-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="b0659-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b0659-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0659-111">/admin</span><span class="sxs-lookup"><span data-stu-id="b0659-111">/admin</span></span>  <br/> |<span data-ttu-id="b0659-112">Führt das Office-Anpassungstool aus, um eine Setupanpassungsdatei (.msp-Datei) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b0659-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="b0659-113">/adminfile [Pfad]</span><span class="sxs-lookup"><span data-stu-id="b0659-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="b0659-p102">Wendet die angegebene Setupanpassungsdatei auf die Installation an. Sie können einen Pfad zu einer bestimmten Anpassungsdatei (.msp-Datei) oder zu dem Ordner angeben, in dem Sie Anpassungsdateien speichern.</span><span class="sxs-lookup"><span data-stu-id="b0659-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="b0659-116">/config [Pfad]</span><span class="sxs-lookup"><span data-stu-id="b0659-116">/config [path]</span></span>  <br/> |<span data-ttu-id="b0659-117">Gibt die Datei config. XML an, die von Setup während der Installation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b0659-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="b0659-118">Verwenden Sie die Option/config, um die Datei config. XML anzugeben, die Sie für Skype for Business-Installationen angepasst haben, beispielsweise:`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="b0659-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="b0659-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="b0659-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="b0659-120">Wird mit einer geänderten config.xml-Datei verwendet, um Setup im Wartungsmodus auszuführen und Änderungen an einer vorhandenen Office-Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="b0659-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="b0659-121">So können Sie beispielsweise die Option/MODIFY verwenden, um Skype for Business-Features hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b0659-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="b0659-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="b0659-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="b0659-123">Führt das Setup vom Computer des Benutzers aus, um Skype for Business zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="b0659-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="b0659-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="b0659-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="b0659-125">Führt das Setup aus, um Skype for Business vom Computer des Benutzers zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b0659-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


