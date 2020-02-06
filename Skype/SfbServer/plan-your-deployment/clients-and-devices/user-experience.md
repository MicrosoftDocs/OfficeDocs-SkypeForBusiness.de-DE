---
title: Planen der Skype for Business 2015-Clientumgebung für Ihre Benutzer
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 'Zusammenfassung: erfahren Sie mehr über die neuen Skype for Business-und die Schritte, die Sie Unternehmen können, um Ihre Umgebung und Ihre Benutzer für das Update vorzubereiten – ganz gleich, ob Sie Skype for Business Online, Skype for Business Server 2019, Skype für Business Server 2015, lync Server 2013 oder Lync Server 2010.'
ms.openlocfilehash: afd0f9f8a764ef9430d9ac1a9887a872c02fedd7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803525"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Planen der Skype for Business 2015-Clientumgebung für Ihre Benutzer
 
**Zusammenfassung:** Informieren Sie sich über die neuen Skype for Business-und die Schritte, die Sie Unternehmen können, um Ihre Umgebung und Ihre Benutzer für das Update vorzubereiten, ganz gleich, ob Sie Skype for Business Online, Skype for Business Server 2019, Skype für Business Server 2015, lync Server 2013 oder lync Server 2010 verwenden.
  
Das 2015-Office-Update für lync 2013 vom 14. April umfasst die neue Benutzeroberfläche von Skype for Business. Mit diesem Update können Administratoren das Aussehen und Verhalten des Clients steuern und entscheiden, ob Sie die lync 2013-Clientumgebung beibehalten oder die verbesserte Skype for Business-Clientumgebung verwenden möchten. Der Skype for Business-Client hat den lync 2013-Client effektiv ersetzt und die Möglichkeit für Administratoren, zwischen der vorhandenen lync-Clientumgebung und der neuen Skype for Business-Clientumgebung zu wählen, hinzugefügt. Informationen zu diesem Update finden Sie unter [April 14, 2015-Update für lync 2013 (Skype for Business) (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/).
  
Am 12. Mai 2015 wird ein weiteres monatliches Update von Office mit dem aktualisierten Skype for Business-Client durchgestellt. Viele Kunden, die das Update vom April nicht angewendet haben, nehmen das 12. Mai-Update für Office 2013 auf. Mit den Informationen in diesem Thema können Sie Ihre Organisation, Ihre Umgebung und Ihre Benutzer für das Client Update vorbereiten. Wenn Sie den Übergang für Ihre Benutzer und Support Teams vereinfachen möchten, verwenden Sie die Informationen in diesem Thema, um zu entscheiden, welche Clientumgebung für die Benutzer erforderlich ist, und nehmen Sie dann die Änderungen an Ihrer Umgebung vor, bevor Sie das Client Update in Ihrer Organisation bereitstellen.
  
- [What client experience do you want for your users?](user-experience.md#clientexperience)
    
- [Vorbereiten Ihrer Umgebung für den Skype for Business-Client](user-experience.md#usinglync)
    
- [Resources to help you prepare your support teams and your end users for the update](user-experience.md#support)
    
> [!NOTE]
> Die lync 2013-Clientumgebung ist keine Option für Skype for Business 2016-Clientversionen. Bevor Sie versuchen, ihre Clientumgebung für die Verwendung des lync 2013-Clients zu konfigurieren, überprüfen Sie die Client Version, um sicherzustellen, dass Sie nicht mit der Zahl 16 beginnt; Beispiel: 16. x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>Welche Clientumgebung wünschen Sie für Ihre Benutzer?
<a name="clientexperience"> </a>

Mit dem neuen Skype for Business-Client können Sie steuern, welche Client-Benutzererfahrung Sie erhalten, entweder lync oder Skype for Business. Die standardmäßige Clientumgebung hängt davon ab, ob Sie lync oder Skype for Business lokal oder Online verwenden. Wenn Sie Skype for Business Online (lync Online) heute mit Office 365 ProPlus, Office 365 Business Premium oder Office 2013 verwenden, ist die aktualisierte Skype for Business-Clientumgebung, inspiriert durch das Aussehen und Verhalten von Skype, die standardmäßige Benutzeroberfläche. Wenn Sie lync Server heute lokal verwenden, ist die lync-Clientumgebung die Standardeinstellung.
  
Sie können mithilfe von Clientrichtlinien konfigurieren, welche Clientumgebung Ihre Benutzer erhalten. Bei einer Clientrichtlinie handelt es sich um eine Gruppe von Konfigurationseinstellungen, die auf Benutzer angewendet werden, wenn Sie sich bei lync oder Skype for Business anmelden.
  
### <a name="skype-for-business-client-experience"></a>Skype for Business-Clientumgebung

Neben allen Funktionen von lync bietet Skype for Business neue Funktionen mit vereinfachten Steuerelementen und vertrauten Symbolen von Skype. Einige neue Funktionen in Skype for Business sind nur mit der neuen Skype for Business-Clientumgebung verfügbar. Weitere Informationen zu den neuen Funktionen in Skype for Business finden Sie unter [Entdecken von Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Lync-Clientumgebung

Die Lync-Clientumgebung ähnelt stark der Lync 2013-Clientumgebung, mit der Ihre Benutzer bereits vertraut sind, aber es gibt einige Änderungen, auf die Sie Ihre Benutzer hinweisen sollten. Informationen zu den Unterschieden zwischen der lync-Clientumgebung und dem lync 2013-Client finden Sie unter [Warum wird Skype for Business angezeigt, wenn ich lync verwende?](https://go.microsoft.com/fwlink/p/?LinkId=544712) und die zusätzlichen Links weiter unten in diesem Thema.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Vorbereiten Ihrer Umgebung für den Skype for Business-Client
<a name="usinglync"> </a>

Es gibt einige Dinge, die Sie erledigen müssen, um Ihre Umgebung für das Clientupdate vorzubereiten. Bevor Sie Änderungen vornehmen, um die Clientumgebung zu konfigurieren, müssen Sie zunächst sicherstellen, dass Sie eine Version von Skype for Business Server oder lync Server verwenden, die die Clientrichtlinien Einstellungen unterstützt.
  
Nachdem Sie bestätigt haben, dass Sie eine Version von Skype for Business Server oder lync Server verwenden, die die Richtlinieneinstellungen unterstützt, um die Clientumgebung zu steuern, müssen Sie die Richtlinieneinstellungen in Ihrer Umgebung konfigurieren. Welche Schritte Sie ausführen müssen, hängt von der Version von Skype for Business Server oder lync Server ab, die Sie verwenden, und davon, ob Ihre Benutzer lokal oder online sind. 
  
Sie sollten diese Änderungen vornehmen, bevor das Client Update an Ihre Benutzer übermittelt wird, damit Sie die Clientumgebung beim ersten Start des Skype for Business-Clients steuern können. In den folgenden Tabellen werden die Schritte beschrieben, die Sie ausführen müssen, um Ihre Umgebung für die gewünschte Clientumgebung für Ihre Benutzer zu konfigurieren.
  
|**Deployment**|**Skype for Business-Clientumgebung**|**Lync-Clientumgebung**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |Außer der Bereitstellung von Clientbuild 4711.1002 (April 2015) oder höher gibt es keine weiteren Schritte.  <br/> |[Verwenden der Lync-Clientumgebung mit Skype for Business Online](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |Außer der Bereitstellung von Clientbuild 4711.1002 (April 2015) oder höher gibt es keine weiteren Schritte.  <br/> |[Verwenden der Lync-Clientumgebung mit einer lokalen Bereitstellung von Skype for Business Server](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 und lync Server 2010  <br/> |[Verwenden der Skype-Clientumgebung mit lync Server 2013 oder lync Server 2010 lokal](user-experience.md#SkypewithLynconprem) <br/> |[Verwenden der lync-Clientumgebung mit lync Server 2013 oder lync Server 2010 lokal](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Verwenden der Skype-Clientumgebung mit lync Server 2013 oder lync Server 2010 lokal
<a name="SkypewithLynconprem"> </a>

Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die Skype-Clientumgebung in einer lokalen Bereitstellung konfigurieren möchten. Dies ist die Standardumgebung für lokale Bereitstellungen.
  
 **Schritt 1:** Stellen Sie zunächst sicher, dass Sie eine Version von lync Server ausführen, die die Clientrichtlinien Einstellungen unterstützt.
  
- **Lync Server 2013** – Sie müssen das kumulative Update vom Dezember 2014 (5.0.8308.857) für lync Server 2013 oder ein höheres Update ausführen. Informationen finden Sie unter [Updates für lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync Server 2010** – Sie müssen das kumulative Update vom Februar 2015 (4.0.7577.710) für lync Server 2010 oder ein höheres Update ausführen. Informationen finden Sie unter [Updates für lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
  **Schritt 2:** Verwenden Sie als nächstes eine Clientrichtlinie, um die Skype-Clientumgebung mit dem Skype for Business-Client einzurichten. Es gibt **3 Optionen** zur Festlegung der Clientumgebung mithilfe einer Clientrichtlinie.
  
  **Option 1:** Legen Sie die Skype-Clientumgebung mithilfe einer globalen Richtlinie fest. Beachten Sie, dass die globale Richtlinie für alle Benutzer in Ihrer Bereitstellung gilt, dass Benutzer- und Standortrichtlinien jedoch Vorrang vor der globalen Richtlinie haben:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Option 2:** Ändern Sie eine vorhandene Clientrichtlinie, die Sie in Ihrer Umgebung verwenden, so ab, dass sie die Einstellung zum Aktivieren der Skype-Clientumgebung enthält. Dadurch können Sie die Skype-Clientumgebung nur für diejenigen Benutzer festlegen, denen die vorhandene Richtlinie zugewiesen ist:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Option 3:** Erstellen Sie eine neue Richtlinie, die Sie Benutzern zuweisen und in der die Einstellung für die Skype-Clientumgebung enthalten ist. Erstellen Sie zunächst die neue Clientrichtlinie und geben Sie den Namen der Richtlinie als Wert für den Parameter **Identity** an:
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

Weisen Sie die Richtlinie dann den Benutzern zu, indem Sie den Namen der Richtlinie (den Wert, den Sie für den Parameter **Identity** verwendet haben) als Wert für den Parameter **PolicyName** verwenden:
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Schritt 3:** Nachdem Sie Ihre Clientrichtlinien konfiguriert haben, müssen Sie den Skype for Business-Client, Build 4711,1002 (April, 2015) oder höher, bereitstellen.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Verwenden der lync-Clientumgebung mit lync Server 2013 oder lync Server 2010 lokal
<a name="LyncwithLynconprem"> </a>

Dies ist die Standard Erfahrung, wenn der Skype for Business-Client in einer lokalen lync Server-Bereitstellung bereitgestellt wird. Sie müssen keine Clientrichtlinien konfigurieren, um die Lync-Clientumgebung zu verwenden, aber es kann sinnvoll sein, das Verhalten des Clients bei der ersten Ausführung zu steuern. Standardmäßig werden beim erstmaligen Starten des Skype for Business-Clients die Skype-Client-Benutzeroberfläche verwendet, und Benutzern wird eine Benachrichtigung angezeigt, die anfordert, den Client neu zu starten, um die lync-Clientumgebung zu erhalten. Sie können Ihre Umgebung auch so konfigurieren, dass die Lync-Clientumgebung bereits angezeigt wird, wenn der Benutzer den Client zum ersten Mal startet, und das Clientlernprogramm deaktivieren, indem Sie die Systemregistrierung auf Clientcomputern ändern. Die Schritte, die Sie ausführen müssen, bevor Sie den Skype for Business-Client bereitstellen, finden Sie unter den folgenden Themen:
  
- **Lync Server 2013**finden Sie unter [Konfigurieren der Clientumgebung mit Skype for Business in lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync Server 2010** siehe [Konfigurieren der Clientumgebung mit Skype for Business in lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Verwenden der Lync-Clientumgebung mit einer lokalen Bereitstellung von Skype for Business Server
<a name="LyncwithSfBServer"> </a>

Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die lync-Clientumgebung in einer lokalen Skype for Business Server-Bereitstellung konfigurieren möchten.
  
Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die Skype-Clientumgebung in einer lokalen Bereitstellung konfigurieren möchten. Dies ist die Standardumgebung für lokale Bereitstellungen.
  
 **Schritt 1:** Stellen Sie zunächst Skype for Business Server bereit.
  
 **Schritt 2:** Verwenden Sie als nächstes eine Clientrichtlinie, um die lync-Clientumgebung mit dem Skype for Business-Client einzurichten. Es gibt **3 Optionen** zur Festlegung der Clientumgebung mithilfe einer Clientrichtlinie.
  
 **Option 1:** Legen Sie die Lync-Clientumgebung mithilfe einer globalen Richtlinie fest. Beachten Sie, dass die globale Richtlinie für alle Benutzer in Ihrer Bereitstellung gilt, dass Benutzer- und Standortrichtlinien jedoch Vorrang vor der globalen Richtlinie haben:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Option 2:** Ändern Sie eine vorhandene Clientrichtlinie, die Sie in Ihrer Umgebung verwenden, so ab, dass sie die Einstellung zum Aktivieren der Lync-Clientumgebung enthält. Dadurch können Sie die Lync-Clientumgebung nur für diejenigen Benutzer festlegen, denen die vorhandene Richtlinie zugewiesen ist:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Option 3:** Erstellen Sie eine neue Richtlinie, die Sie Benutzern zuweisen und in der die Einstellung für die Lync-Clientumgebung enthalten ist. Erstellen Sie zunächst die neue Clientrichtlinie und geben Sie den Namen der Richtlinie als Wert für den Parameter **Identity** an:
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

Weisen Sie die Richtlinie dann den Benutzern zu, indem Sie den Namen der Richtlinie (den Wert, den Sie für den Parameter **Identity** verwendet haben) als Wert für den Parameter **PolicyName** verwenden:
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Schritt 3: optional** – Standardmäßig wird beim erstmaligen Starten des Skype for Business-Clients die Skype-Client-Benutzeroberfläche verwendet, und Benutzern wird eine Benachrichtigung angezeigt, in der Sie aufgefordert werden, den Client neu zu starten, um die lync-Clientumgebung zu erhalten. Sie können Ihre Umgebung auch so konfigurieren, dass die Lync-Clientumgebung bereits angezeigt wird, wenn der Benutzer den Client zum ersten Mal startet, und das Clientlernprogramm deaktivieren, indem Sie die Systemregistrierung auf Clientcomputern ändern. Die Schritte, die Sie ausführen müssen, bevor Sie den Skype for Business-Client bereitstellen, finden Sie unter [Konfigurieren der Clientumgebung mit Skype for Business](../../deploy/deploy-clients/configure-the-client-experience.md).
  
 **Schritt 4:** Nachdem Sie Ihre Clientrichtlinien konfiguriert haben, müssen Sie den Skype for Business-Client, Build 4711,1002 (April, 2015) oder höher, bereitstellen.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Verwenden der Lync-Clientumgebung mit Skype for Business Online
<a name="LyncwithSfBO"> </a>

Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die lync-Clientumgebung und die Verwendung von Skype for Business Online konfigurieren möchten.
  
Wenn Sie Skype for Business Online verwenden, können Sie die lync-Clientumgebung weiterhin mit dem Skype for Business-Client in Ihrer Organisation verwenden, indem Sie mithilfe der Remote-PowerShell Clientrichtlinien konfigurieren. Es gibt **3 Optionen** zur Festlegung der Clientumgebung mithilfe einer Clientrichtlinie. Beachten Sie, dass sich die Richtlinien-und Parameternamen von den Einstellungen unterscheiden, die Sie zum Konfigurieren der Clientumgebung verwenden, wenn Sie Skype for Business oder lync Server lokal verwenden.
  
 **Option 1:** Stellen Sie die lync-Clientumgebung mithilfe einer globalen Richtlinie ein. Beachten Sie, dass Client-und Website Richtlinien, die auf Benutzer angewendet werden, Vorrang vor einer globalen Richtlinie haben.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 2:** Ändern Sie eine vorhandene Clientrichtlinie, die Sie in Ihrer Umgebung verwenden, so ab, dass sie die Einstellung zum Aktivieren der Lync-Clientumgebung enthält. Dadurch können Sie die Lync-Clientumgebung nur für diejenigen Benutzer festlegen, denen die vorhandene Richtlinie zugewiesen ist:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 3:** Verwenden Sie eine benutzerdefinierte Richtlinieninstanz, die die Einstellung für die lync-Clientumgebung umfasst.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Nachdem Sie Ihre Clientrichtlinien konfiguriert haben, müssen Sie den Skype for Business-Client, Build 4711,1002 (April, 2015) oder höher, bereitstellen.
  
Detaillierte Informationen dazu, wie Sie die Clientumgebung mit Skype for Business Online konfigurieren, einschließlich der Schritte zum Steuern der ersten Ausführung und PowerShell-Skripts, die Sie zum Konfigurieren Ihrer Umgebung verwenden können, finden Sie unter [Wechseln zwischen den Benutzeroberflächen von Skype for Business und lync-Client](https://aka.ms/SfBOUI).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Ressourcen zur besseren Vorbereitung Ihrer Supportteams und Endbenutzer auf das Update
<a name="support"> </a>

Damit Sie und Ihre Organisation sich auf den Übergang vorbereiten können, stehen Ihnen zahlreiche zusätzliche Ressourcen zur Verfügung, die Ihnen bei der Planung, Schulung und Einbindung von Endbenutzern helfen.
  
- [Video: Einführung in Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Schnell Start Handbücher für Skype for Business (Download)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync ist jetzt Skype for Business – sehen Sie, was es neues gibt.](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for Business: Schritt-für-Schritt-Anleitung für neue Benutzer](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Warum wird Skype for Business angezeigt, wenn ich lync verwende?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

