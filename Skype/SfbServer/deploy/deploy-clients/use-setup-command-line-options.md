---
title: Verwenden der Setup-Befehlszeilenoptionen in Skype for Business Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Zusammenfassung: Erfahren Sie mehr über Setup.exe Befehlszeile Vorgänge während des Setups von Office.'
ms.openlocfilehash: 0fa4f31750697f0bd0dbe87bbde025cbc7f530bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="use-setup-command-line-options-in-skype-for-business-server-2015"></a><span data-ttu-id="0742e-103">Verwenden der Setup-Befehlszeilenoptionen in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0742e-103">Use Setup command-line options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0742e-104">**Zusammenfassung:** Informationen Sie zu Setup.exe Befehlszeile Vorgänge während des Setups von Office.</span><span class="sxs-lookup"><span data-stu-id="0742e-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="0742e-105">Die Befehlszeile von "Setup.exe" wird nur für wenige Vorgänge des Office-Setups verwendet.</span><span class="sxs-lookup"><span data-stu-id="0742e-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="0742e-106">Verwenden Sie die Setup-Befehlszeilenoptionen, sondern in der Regel verwenden Office-Anpassungstool und der Datei Config.xml für Produkt-Setup und Anpassung Sie.</span><span class="sxs-lookup"><span data-stu-id="0742e-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="0742e-107">Die Befehlszeile der Office "Setup.exe" erkennt die in der folgenden Tabelle beschriebenen Befehlzeilenoptionen.</span><span class="sxs-lookup"><span data-stu-id="0742e-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="0742e-108">**Office-Setup-Befehlszeilenoptionen**</span><span class="sxs-lookup"><span data-stu-id="0742e-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="0742e-109">**Setup-Befehlszeilenoption**</span><span class="sxs-lookup"><span data-stu-id="0742e-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="0742e-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0742e-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0742e-111">/admin</span><span class="sxs-lookup"><span data-stu-id="0742e-111">/admin</span></span>  <br/> |<span data-ttu-id="0742e-112">Führt das Office-Anpassungstool aus, um eine Setupanpassungsdatei (.msp-Datei) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0742e-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="0742e-113">/adminfile [Pfad]</span><span class="sxs-lookup"><span data-stu-id="0742e-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="0742e-p102">Wendet die angegebene Setupanpassungsdatei auf die Installation an. Sie können einen Pfad zu einer bestimmten Anpassungsdatei (.msp-Datei) oder zu dem Ordner angeben, in dem Sie Anpassungsdateien speichern.</span><span class="sxs-lookup"><span data-stu-id="0742e-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="0742e-116">/config [Pfad]</span><span class="sxs-lookup"><span data-stu-id="0742e-116">/config [path]</span></span>  <br/> |<span data-ttu-id="0742e-117">Gibt die Datei Config.xml, die Setup während der Installation verwendet.</span><span class="sxs-lookup"><span data-stu-id="0742e-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="0742e-118">Verwenden Sie die Option/config auf die Datei Config.xml angeben, die Sie für Skype für Business-Installationen, beispielsweise angepasst:`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="0742e-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="0742e-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="0742e-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="0742e-120">Wird mit einer geänderten config.xml-Datei verwendet, um Setup im Wartungsmodus auszuführen und Änderungen an einer vorhandenen Office-Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="0742e-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="0742e-121">Angenommen, Sie können die / modify Option zum Hinzufügen oder Entfernen von Skype für Business-Features.</span><span class="sxs-lookup"><span data-stu-id="0742e-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="0742e-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="0742e-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="0742e-123">Führt Setup aus dem Computer des Benutzers, Skype für Unternehmen zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="0742e-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="0742e-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="0742e-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="0742e-125">Führt Setup aus, um Skype für Unternehmen aus dem Computer des Benutzers zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="0742e-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   
<span data-ttu-id="0742e-126">Ausführliche Informationen zum Verwenden der Setup-Befehlszeilenoptionen finden Sie unter [https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515).</span><span class="sxs-lookup"><span data-stu-id="0742e-126">For details about using the setup command-line options, see [https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515).</span></span> 
  

