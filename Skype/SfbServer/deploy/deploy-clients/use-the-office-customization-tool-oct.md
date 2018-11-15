---
title: Verwenden Sie das Office-Anpassungstool (OAT) in Skype für Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Zusammenfassung: Informationen zum Office-Anpassungstool mit der Skype für Business-Client verwenden.'
ms.openlocfilehash: 6050a9e9c36fa62aff16994469e63a9689ab5958
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530678"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="ddf46-103">Verwenden Sie das Office-Anpassungstool (OAT) in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="ddf46-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="ddf46-104">**Zusammenfassung:** Verwendung von Office-Anpassungstool mit der Skype für Business-Client.</span><span class="sxs-lookup"><span data-stu-id="ddf46-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="ddf46-105">Office-Anpassungstool (OAT) ist Teil des Setup-Programms und ist das empfohlene Tool für viele Anpassungen.</span><span class="sxs-lookup"><span data-stu-id="ddf46-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="ddf46-106">Mithilfe des OAT Anpassen von Office und Ihre Anpassungen in einer MSP-Setupanpassungsdatei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ddf46-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="ddf46-107">Platzieren Sie die Datei in den Ordner Updates im Netzwerkinstallationspfad.</span><span class="sxs-lookup"><span data-stu-id="ddf46-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="ddf46-108">Bei der Installation von Office wird Setup für eine Setupanpassungsdatei im Ordner Updates sucht und wendet die Anpassungen.</span><span class="sxs-lookup"><span data-stu-id="ddf46-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="ddf46-109">Der Ordner "Updates" kann nur für das Bereitstellen von Softwareupdates bei einer Erstinstallation von Office verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ddf46-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="ddf46-110">Office-Anpassungstool ist Teil der Installation, und es wird nur für Volumenlizenzversionen des Produkts verwendet.</span><span class="sxs-lookup"><span data-stu-id="ddf46-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="ddf46-111">Führen Sie Office-Anpassungstool, indem Sie eingeben `setup.exe /admin` an der Befehlszeile im Stammverzeichnis des Netzwerkinstallationspfads, die die Office-Quelldateien.</span><span class="sxs-lookup"><span data-stu-id="ddf46-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="ddf46-112">Verwenden Sie beispielsweise folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="ddf46-112">For example, use the following:</span></span>
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="ddf46-113">Administratoren verwenden das OAT zum Erstellen einer Setupanpassungsdatei MSP-Datei und die folgenden Bereiche anpassen können:</span><span class="sxs-lookup"><span data-stu-id="ddf46-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="ddf46-114">**Setup** Anzeigen Sie Ebene, frühere Versionen von Office entfernt, benutzerdefinierte Programme, die während der ausgeführt werden verwendet, um die Standard-Installationsspeicherort angeben, auf dem Client und Standardwerte in der Name der Organisation, zusätzliche netzwerkinstallationsquellen, Produktschlüssel, Endbenutzer-Lizenzvertrag, Installation, Sicherheitseinstellungen und Setup-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="ddf46-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="ddf46-115">**Features** So konfigurieren Sie benutzereinstellungen sowie zum Anpassen der Installation von Office-Features verwendet.</span><span class="sxs-lookup"><span data-stu-id="ddf46-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="ddf46-116">Administratoren können mithilfe des OAT anfängliche Standardwerte für Office-Anwendungseinstellungen für Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="ddf46-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="ddf46-117">Benutzer können die meisten Einstellungen nach der Installation ändern.</span><span class="sxs-lookup"><span data-stu-id="ddf46-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="ddf46-118">**Weitere Inhalte** Zum Hinzufügen oder Entfernen von Dateien, hinzufügen oder Entfernen von Registrierungseinträgen und Konfigurieren von Verknüpfungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ddf46-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="ddf46-119">**Outlook** Zum Anpassen von Outlook-Standardprofils des Benutzers verwendet, Exchange-Einstellungen angeben, Konten hinzufügen, Entfernen von Konten und exporteinstellungen und Senden-Empfangen-Gruppen angeben.</span><span class="sxs-lookup"><span data-stu-id="ddf46-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="ddf46-120">Informationen zum OAT finden Sie unter [mithilfe des OAT zum Anpassen von Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span><span class="sxs-lookup"><span data-stu-id="ddf46-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="ddf46-121">Beachten Sie, dass diese Informationen auch für spätere Versionen von Office gilt.</span><span class="sxs-lookup"><span data-stu-id="ddf46-121">Note that this information also applies to later versions of Office.</span></span>
  

