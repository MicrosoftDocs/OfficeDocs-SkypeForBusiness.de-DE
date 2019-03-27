---
title: 'Verwalten von Zugriffsnummern für einwahlkonferenzen in Skype für Business Server '
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Zusammenfassung: Informationen Sie zum Verwalten von Zugriffsnummern für einwahlkonferenzen in Skype für Business Server.'
ms.openlocfilehash: c074cb9417e39d8964996f643b90f8fe3e0fd7b7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883521"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a><span data-ttu-id="b04b5-103">Verwalten von Zugriffsnummern für einwahlkonferenzen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="b04b5-103">Manage dial-in conferencing access numbers in Skype for Business Server</span></span>
 
<span data-ttu-id="b04b5-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie Zugriffsnummern für einwahlkonferenzen in Skype für Business Server verwalten.</span><span class="sxs-lookup"><span data-stu-id="b04b5-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.</span></span>
  
<span data-ttu-id="b04b5-105">Beim Bereitstellen von Einwahlkonferenzen müssen Sie Telefonnummern einrichten, die Benutzer aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) wählen können, um am Audioteil einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="b04b5-105">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="b04b5-106">Diese Zugriffsnummern für die Einwahl werden in Besprechungseinladungen und auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b04b5-106">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="b04b5-107">In diesem Themenbereich wird beschrieben, wie bestehende Zugriffsnummern für Einwahlkonferenzen angezeigt, geändert oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="b04b5-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="b04b5-108">Weitere Informationen zum Erstellen der anfänglichen Einwahl Zugriffsnummern finden Sie unter [Configure einwahlkonferenzen in Skype für Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="b04b5-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="b04b5-109">Anzeigen von Zugriffsnummern für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="b04b5-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="b04b5-110">Sie können die Zugriffsnummern für einwahlkonferenzen mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b04b5-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b04b5-111">Ansicht Einwahl Zugriffsnummern mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="b04b5-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b04b5-112">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="b04b5-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="b04b5-113">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="b04b5-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b04b5-114">Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.</span><span class="sxs-lookup"><span data-stu-id="b04b5-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="b04b5-115">Klicken Sie auf der Seite **Zugriffsnummer für Einwahlkonferenz** auf die Zugriffsnummer, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="b04b5-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="b04b5-116">Aktivieren Sie unter **Bearbeiten** das Kontrollkästchen **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="b04b5-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b04b5-117">Ansicht Einwahl Zugriffsnummern mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="b04b5-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b04b5-118">Verwenden Sie das Cmdlet **Get-CsDialInConferencingAccessNumber**, um Informationen über Zugriffsnummern für die Einwahl anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b04b5-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="b04b5-119">Der folgende Befehl gibt eine Auflistung von allen einwahlkonferenzen Zugriffsnummern für die Verwendung in der Organisation konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="b04b5-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```
Get-CsDialInConferencingAccessNumber
```

<span data-ttu-id="b04b5-120">Im Folgenden finden Sie ein Beispiel für die Art der zurückgegebenen Informationen:</span><span class="sxs-lookup"><span data-stu-id="b04b5-120">The following is an example of the type of information returned:</span></span>
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

<span data-ttu-id="b04b5-121">Weitere Informationen finden Sie unter [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b04b5-121">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="b04b5-122">Zugriffsnummern für Einwahlkonferenzen ändern</span><span class="sxs-lookup"><span data-stu-id="b04b5-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="b04b5-123">Sie können die Zugriffsnummer für Einwahl-Zugriffsnummern mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell ändern.</span><span class="sxs-lookup"><span data-stu-id="b04b5-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b04b5-124">Ändern der Einwahl Zugriffsnummern mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="b04b5-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b04b5-125">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="b04b5-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="b04b5-126">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="b04b5-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b04b5-127">Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.</span><span class="sxs-lookup"><span data-stu-id="b04b5-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="b04b5-128">Klicken Sie auf der Seite **Zugriffsnummer für die Einwahl** auf eine der Einwahlnummern in der Liste, anschließend auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="b04b5-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b04b5-p103">Die Suche nach den Inhalten einer Spalte in der Liste der Zugriffsnummern für die Einwahl über das Suchfeld führt möglicherweise nicht zu den erwarteten Ergebnissen. Sortieren Sie die Liste stattdessen nach der gewünschten Spalte, um nach der Zugriffsnummer für die Einwahl zu suchen, die Sie anzeigen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="b04b5-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="b04b5-131">Geben Sie im Feld **Anzeigenummer** die Telefonnummer ein, die PSTN-Telefonbenutzer (Public Switched Telephone Network, Telefonfestnetz) wählen, um an einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="b04b5-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="b04b5-132">Diese Nummer wird in Besprechungseinladungen und auf der Webseite mit den Einstellungen für die Einwahlkonferenz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b04b5-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="b04b5-133">Geben Sie in **Anzeigename** eine Beschreibung für die Zugriffsnummer für die Einwahl ein.</span><span class="sxs-lookup"><span data-stu-id="b04b5-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="b04b5-134">Dies ist der Name, der die Anzahl DFÜ-Zugriff in Skype für Suchergebnisse Business zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b04b5-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="b04b5-135">Der Name wird im Client angezeigt, wenn ein Benutzer die Einwahlnummer wählt.</span><span class="sxs-lookup"><span data-stu-id="b04b5-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="b04b5-p105">Geben Sie im Feld **Anschluss-URI** die E.164-Nummer der Zugriffsnummer für die Einwahl im TEL-URI-Format ein, einschließlich des +-Symbols vor der Nummer und ohne Leerzeichen. Beispiel: tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="b04b5-p105">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b04b5-138">Dieser Anschluss-URI kann nicht für eine andere Einwahlnummer für Einwahlkonferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b04b5-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="b04b5-139">Führen Sie unter **SIP-URI** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="b04b5-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="b04b5-140">Geben Sie in das Textfeld einen eindeutigen SIP-URI für diese Zugriffsnummer für Einwahlkonferenzen ein.</span><span class="sxs-lookup"><span data-stu-id="b04b5-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="b04b5-141">SIP-URI ist in verschiedenen Standorten, einschließlich angezeigt, aber nicht beschränkt, um Benachrichtigungen und früheren Versionen von Lync-Clients aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b04b5-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b04b5-p107">Dieser SIP-URI kann nicht für eine andere Zugriffsnummer für Einwahlkonferenzen verwendet werden. Der SIP-URI kann nach der Erstellung der Zugriffsnummer nicht geändert werden. Die einzige Möglichkeit zum Ändern des SIP-URI besteht darin, die Zugriffsnummer zu löschen und neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b04b5-p107">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="b04b5-145">Klicken Sie im Dropdown-Listenfeld auf die Domäne der Konferenzzentrale Anwendung, die diese Zugriffsnummer für Einwahl unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b04b5-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="b04b5-146">Klicken Sie unter **Pool** auf den Pool, der die Instanz der Konferenzzentrale ausführt, die diese Einwahlnummer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b04b5-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b04b5-147">Wenn der Pool nach dem Erstellen der Zugriffsnummer geändert werden muss, müssen Sie das Cmdlet **Move-CsApplicationEndpoint** verwenden oder die Zugriffsnummer löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b04b5-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="b04b5-148">Klicken Sie unter **Primäre Sprache** auf die Sprache, in der Ansagen für diese Einwahlnummer wiedergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b04b5-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="b04b5-p108">Bei der primären Sprache handelt es sich um die Sprache, die die Konferenzzentrale zum Beantworten des Anrufs verwendet. Die unterstützten Sprachen werden auf der Webseite mit den Einstellungen für die Einwahlkonferenz neben den verschiedenen Zugriffsnummern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b04b5-p108">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="b04b5-151">(Optional) Klicken Sie unter **Sekundäre Sprachen (maximal vier)** auf **Hinzufügen**, wählen Sie eine oder mehrere zusätzliche Sprachen aus, die für Anrufer dieser Zugriffsnummer für die Einwahl unterstützt werden sollen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b04b5-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="b04b5-p109">Sie können für jede Zugriffsnummer für die Einwahl bis zu vier sekundäre Sprachen auswählen. Benutzer können beim Einwählen in eine Konferenz eine sekundäre Sprache auswählen, bevor sie die Konferenz-ID eingeben.</span><span class="sxs-lookup"><span data-stu-id="b04b5-p109">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="b04b5-154">Klicken Sie auf **Hinzufügen**, klicken Sie auf einen oder mehrere Bereiche, die für diese Nummer Einwahlnummern Wählpläne zugeordnet sind, und klicken Sie dann auf **OK**, um eine Region für die Anzahl DFÜ-Zugriff unter **zugeordnete Regionen**, hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b04b5-154">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="b04b5-155">Zum Löschen einer Region aus der Einwahlnummer klicken Sie unter **Zugeordnete Regionen** auf die zu löschende Region und anschließend auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="b04b5-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="b04b5-156">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b04b5-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b04b5-157">Ändern der Einwahl Zugriffsnummern mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="b04b5-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b04b5-158">Verwenden Sie das Cmdlet **Set-CsDialInConferencingAccessNumber**, um die Zugriffsnummern für die Einwahl zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b04b5-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="b04b5-p110">Der folgende Befehl ändert die Eigenschaft „DisplayName“ für die Zugriffsnummer für Einwahlkonferenzen mit dem Identitätswert „sip:RedmondDialIn@litwareinc.com“. In diesem Beispiel wurde als Anzeigename „Redmond Dial-In Access Number“ festgelegt:</span><span class="sxs-lookup"><span data-stu-id="b04b5-p110">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com. In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

<span data-ttu-id="b04b5-p111">In nächsten Beispiel wird die Zugriffsnummer für Einwahlkonferenzen mit dem Identitätswert „sip:RedmondDialIn@litwareinc.com“ geändert, um zwei Regionen anzugeben: „Redmond“ und „Seattle“. Hierzu wird der Parameter „Region“ aufgerufen, gefolgt von den beiden Regionen (zwei durch Kommas voneinander getrennte Werte). Beachten Sie, dass beim Ausführen dieses Befehls ein Fehler auftreten kann, wenn die beiden Regionen („Redmond“ und „Seattle“) noch nicht in den Wähleinstellungen definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b04b5-p111">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle. To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas). Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

<span data-ttu-id="b04b5-164">Weitere Informationen finden Sie unter [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b04b5-164">For more information, see [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="b04b5-165">Löschen einer Zugriffsnummer für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="b04b5-165">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="b04b5-166">Sie können eine Zugriffsnummer für einwahlkonferenzen mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell löschen.</span><span class="sxs-lookup"><span data-stu-id="b04b5-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b04b5-167">Löschen einer Zugriffsnummer für einwahlkonferenzen mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="b04b5-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="b04b5-168">Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .</span><span class="sxs-lookup"><span data-stu-id="b04b5-168">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="b04b5-169">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="b04b5-169">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b04b5-170">Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.</span><span class="sxs-lookup"><span data-stu-id="b04b5-170">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="b04b5-171">Klicken Sie auf der Seite auf die Einwahlnummer, die Sie aus der Liste löschen möchten, dann auf **Bearbeiten** und schließlich auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="b04b5-171">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="b04b5-172">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b04b5-172">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b04b5-173">Löschen einer Zugriffsnummer für einwahlkonferenzen mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="b04b5-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b04b5-174">Über **Remove-CsDialInConferencingAccessNumber** löschen Sie eine Einwahlnummer für Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="b04b5-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="b04b5-175">Mit dem folgenden Befehl wird die Zugriffsnummer für Einwahlkonferenzen mit der Identität „sip:RedmondDialInAccess@litwareinc.com“ gelöscht:</span><span class="sxs-lookup"><span data-stu-id="b04b5-175">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="b04b5-176">Mit dem folgenden Befehl werden alle Zugriffsnummern für Einwahlkonferenzen gelöscht, die der Region „Northwest“ zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="b04b5-176">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="b04b5-177">Mit dem folgenden Befehl werden alle Zugriffsnummern für Einwahlkonferenzen mit der primären Sprache Italienisch gelöscht:</span><span class="sxs-lookup"><span data-stu-id="b04b5-177">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="b04b5-178">Weitere Informationen finden Sie unter [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b04b5-178">For more information, see [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  

