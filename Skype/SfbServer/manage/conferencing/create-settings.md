---
title: Erstellen von besprechungskonfigurationseinstellungen in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Zusammenfassung: Informationen zum Erstellen von besprechungskonfigurationseinstellungen in Skype für Business Server.'
ms.openlocfilehash: ea75e133ab15f450a6316c9ee86ba2ded485f29a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919416"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="8053f-103">Erstellen von besprechungskonfigurationseinstellungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="8053f-103">Create meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="8053f-104">**Zusammenfassung:** Informationen zum Erstellen von besprechungskonfigurationseinstellungen in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="8053f-104">**Summary:** Learn how to create meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="8053f-105">Sie können erstellen besprechungskonfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="8053f-105">You can create meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8053f-106">Erstellen von besprechungskonfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="8053f-106">Create meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8053f-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="8053f-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="8053f-108">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="8053f-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8053f-109">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Besprechungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="8053f-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="8053f-110">Klicken Sie auf der Seite **Besprechungskonfiguration** auf **Neu** und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="8053f-110">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
    - <span data-ttu-id="8053f-p101">Klicken Sie auf **Standortkonfiguration**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie Einstellungen für den Besprechungsbeitritt definieren möchten. Klicken Sie in der resultierenden Liste der Standorte auf den gewünschten Standort und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8053f-p101">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
    - <span data-ttu-id="8053f-p102">Klicken Sie auf **Poolkonfiguration**, um eine Richtlinie auf Poolebene zu erstellen. Geben Sie im Suchfeld **Dienst auswählen** einen Teil oder den gesamten Namen des Pooldienstes ein, für den Sie Einstellungen für den Besprechungsbeitritt definieren möchten. Klicken Sie in der resultierenden Liste der Dienste auf den gewünschten Pool und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8053f-p102">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="8053f-p103">Deaktivieren Sie das Kontrollkästchen **PSTN-Anrufer umgehen Wartebereich**, um Teilnehmer, die sich über das Festnetz einwählen, zunächst an den Wartebereich weiterzuleiten. In der Standardeinstellung gelangen Anrufer, die sich über das Festnetz einwählen, direkt zur Besprechung.</span><span class="sxs-lookup"><span data-stu-id="8053f-p103">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>
    
6. <span data-ttu-id="8053f-119">Legen Sie im Abschnitt **Als Referenten festlegen** fest, wer in der Besprechung als Referent agieren kann:</span><span class="sxs-lookup"><span data-stu-id="8053f-119">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
   - <span data-ttu-id="8053f-120">Klicken Sie auf **Keiner**, um nur dem Organisator die Rolle des Referenten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="8053f-120">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
   - <span data-ttu-id="8053f-p104">Klicken Sie auf **Unternehmen**, um nur denjenigen Teilnehmern die Funktion des Referenten zu ermöglichen, die Mitglieder Ihrer Organisation sind. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="8053f-p104">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
   - <span data-ttu-id="8053f-123">Klicken Sie auf **Jeder**, um allen Teilnehmern das Agieren als Referent zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8053f-123">To allow any participants to be a presenter, click **Everyone**.</span></span>
    
7. <span data-ttu-id="8053f-p105">Wenn der Organisator bei der Planung einer Besprechung einen Konferenztyp auswählen soll, deaktivieren Sie das Kontrollkästchen **Konferenztyp standardmäßig zugewiesen**. In der Standardeinstellung wird der Konferenztyp automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="8053f-p105">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>
    
8. <span data-ttu-id="8053f-p106">Wenn Sie verhindern möchten, dass anonyme (nicht authentifizierte) Benutzer automatisch zugelassen werden, deaktivieren Sie das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen**. In der Standardeinstellung werden anonyme Benutzer automatisch für Besprechungen zugelassen.</span><span class="sxs-lookup"><span data-stu-id="8053f-p106">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>
    
9. <span data-ttu-id="8053f-128">Führen Sie die folgenden Schritte aus, um die Besprechungseinladung anzupassen, die an die Teilnehmer gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="8053f-128">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="8053f-129">Beachten Sie, dass für URLs und den benutzerdefinierten Fußzeilentext eine maximale Größe von 1 KB gilt.</span><span class="sxs-lookup"><span data-stu-id="8053f-129">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="8053f-130">Wenn Sie, mit Ausnahme von **Hilfe-URL**, keinen Wert für die Anpassungen angeben, werden sie nicht in die Besprechung aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="8053f-130">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="8053f-131">Wenn Sie eine benutzerdefinierte Hilfe-URL nicht verwenden, wird die Standard-URL für die Hilfe für Skype für Unternehmen einladen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8053f-131">If you do not include a custom help URL, the default help URL for Skype for Business will be displayed in the invite.</span></span> 
    
   - <span data-ttu-id="8053f-p108">Zum Anpassen des Logos, das in der Besprechungseinladung angezeigt wird, geben Sie in **Logo-URL** den Speicherort des Logos ein. Das Logo muss ein GIF- oder JPG-Bild mit einer Größe von 188 x 30 Pixel sein.</span><span class="sxs-lookup"><span data-stu-id="8053f-p108">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo. The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span> 
    
   - <span data-ttu-id="8053f-134">Zum Anpassen des Hilfetexts, der in der Besprechungseinladung angezeigt wird, geben Sie in **Hilfe-URL** den Speicherort des Hilfetexts ein.</span><span class="sxs-lookup"><span data-stu-id="8053f-134">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
   - <span data-ttu-id="8053f-135">Zum Anpassen der rechtlichen Hinweise, die in der Besprechungseinladung angezeigt werden, geben Sie in **URL zu rechtlichen Hinweisen** den Speicherort der rechtlichen Hinweise ein.</span><span class="sxs-lookup"><span data-stu-id="8053f-135">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
   - <span data-ttu-id="8053f-136">Zum Anpassen des Fußzeilentexts, der in der Besprechungseinladung angezeigt wird, geben Sie in **Benutzerdefinierter Fußzeilentext** Text ein.</span><span class="sxs-lookup"><span data-stu-id="8053f-136">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>
    
10. <span data-ttu-id="8053f-137">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8053f-137">Click **Commit**.</span></span>
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8053f-138">Erstellen von besprechungskonfigurationseinstellungen mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="8053f-138">Create meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="8053f-139">Verwenden Sie das **New-CsMeetingConfiguration**-Cmdlet, um Besprechungskonfigurationseinstellungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8053f-139">To create meeting configuration settings, use the **New-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="8053f-140">Mit dem folgenden Befehl wird ein neuer Satz von Besprechungskonfigurationseinstellungen für den Standort „Redmond“ erstellt:</span><span class="sxs-lookup"><span data-stu-id="8053f-140">The following command creates a new set of meeting configuration settings for the Redmond site:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="8053f-141">Da im vorherigen Befehl keine weiteren Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, werden in den neuen Besprechungskonfigurationseinstellungen für alle Eigenschaften die Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="8053f-141">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>
  
<span data-ttu-id="8053f-p109">Um Einstellungen zu erstellen, die andere Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und Parameterwert ein. Wenn Sie beispielsweise eine Auflistung von Besprechungskonfigurationseinstellungen erstellen möchten, die standardmäßig jeden als Referent zu einer Besprechung zulassen, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="8053f-p109">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="8053f-p110">Mehrere Eigenschaftswerte können eingestellt werden, indem Sie mehrere Parameter angeben. Beispielsweise wird mit dem folgenden Befehl jeder als Referent zu einer Besprechung zugelassen und außerdem werden PSTN-Benutzer gezwungen, im Wartebereich zu warten, bis sie formell zur Besprechung zugelassen werden:</span><span class="sxs-lookup"><span data-stu-id="8053f-p110">Multiple property values can be set by including multiple parameters. For example, the following command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

<span data-ttu-id="8053f-146">Weitere Informationen sowie eine vollständige Liste der Parameter finden Sie unter [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8053f-146">For more information, including a complete list of parameters, see [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span></span>
  

