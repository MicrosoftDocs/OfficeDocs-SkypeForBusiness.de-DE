---
title: Verwenden von Setup-Befehlszeilenoptionen mit Skype für Business-clients
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Zusammenfassung: Erfahren Sie mehr über Setup.exe Befehlszeile Vorgänge während des Setups von Office.'
ms.openlocfilehash: d3bf2b4d867fbbb43c346f2b9572de329ec66bdc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214877"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="3711e-103">Verwenden von Setup-Befehlszeilenoptionen mit Skype für Business-clients</span><span class="sxs-lookup"><span data-stu-id="3711e-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="3711e-104">**Zusammenfassung:** Informationen Sie zu Setup.exe Befehlszeile Vorgänge während des Setups von Office.</span><span class="sxs-lookup"><span data-stu-id="3711e-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="3711e-105">Die Befehlszeile von "Setup.exe" wird nur für wenige Vorgänge des Office-Setups verwendet.</span><span class="sxs-lookup"><span data-stu-id="3711e-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="3711e-106">Verwenden Sie die Setup-Befehlszeilenoptionen, sondern in der Regel verwenden Office-Anpassungstool und der Datei Config.xml für Produkt-Setup und Anpassung Sie.</span><span class="sxs-lookup"><span data-stu-id="3711e-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="3711e-107">Die Befehlszeile der Office "Setup.exe" erkennt die in der folgenden Tabelle beschriebenen Befehlzeilenoptionen.</span><span class="sxs-lookup"><span data-stu-id="3711e-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="3711e-108">**Optionen der Office Setup-Befehlszeile**</span><span class="sxs-lookup"><span data-stu-id="3711e-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="3711e-109">**Option der Office Setup-Befehlszeile**</span><span class="sxs-lookup"><span data-stu-id="3711e-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="3711e-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3711e-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3711e-111">/admin</span><span class="sxs-lookup"><span data-stu-id="3711e-111">/admin</span></span>  <br/> |<span data-ttu-id="3711e-112">Führt das Office-Anpassungstool aus, um eine Setupanpassungsdatei (.msp-Datei) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3711e-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="3711e-113">/adminfile [Pfad]</span><span class="sxs-lookup"><span data-stu-id="3711e-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="3711e-p102">Wendet die angegebene Setupanpassungsdatei auf die Installation an. Sie können einen Pfad zu einer bestimmten Anpassungsdatei (.msp-Datei) oder zu dem Ordner angeben, in dem Sie Anpassungsdateien speichern.</span><span class="sxs-lookup"><span data-stu-id="3711e-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="3711e-116">/config [Pfad]</span><span class="sxs-lookup"><span data-stu-id="3711e-116">/config [path]</span></span>  <br/> |<span data-ttu-id="3711e-117">Gibt die Datei Config.xml, die Setup während der Installation verwendet.</span><span class="sxs-lookup"><span data-stu-id="3711e-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="3711e-118">Verwenden Sie die Option/config auf die Datei Config.xml angeben, die Sie für Skype für Business-Installationen, beispielsweise angepasst:`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="3711e-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="3711e-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="3711e-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="3711e-120">Wird mit einer geänderten config.xml-Datei verwendet, um Setup im Wartungsmodus auszuführen und Änderungen an einer vorhandenen Office-Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="3711e-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="3711e-121">Angenommen, Sie können die / modify Option zum Hinzufügen oder Entfernen von Skype für Business-Features.</span><span class="sxs-lookup"><span data-stu-id="3711e-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="3711e-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="3711e-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="3711e-123">Führt Setup aus dem Computer des Benutzers, Skype für Unternehmen zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="3711e-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="3711e-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="3711e-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="3711e-125">Führt Setup aus, um Skype für Unternehmen aus dem Computer des Benutzers zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="3711e-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


