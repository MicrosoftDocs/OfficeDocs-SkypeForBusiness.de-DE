---
title: Planen der Skype for Business 2015 Clientumgebung für Ihre Benutzer
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
description: 'Zusammenfassung: Hier erfahren Sie mehr über die neuen Skype for Business und die Schritte, die Sie zur Vorbereitung Ihrer Umgebung und ihrer Benutzer auf das Update durchführen können, unabhängig davon, ob Sie Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015, lync Server 2013 oder lync Server 2010 verwenden.'
ms.openlocfilehash: c1fecbdb5a4ec0a19e464a57ee128d2d00ad501f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777750"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Planen der Skype for Business 2015 Clientumgebung für Ihre Benutzer
 
**Zusammenfassung:** Erfahren Sie mehr über die neuen Skype for Business und die Schritte, die Sie ausführen können, um Ihre Umgebung und Ihre Benutzer für das Update vorzubereiten, unabhängig davon, ob Sie Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015, lync Server 2013 oder lync Server 2010 verwenden.
  
Das Office-Update für lync 2013 vom 14. April 2015 enthält die neue Skype for Business-Benutzeroberfläche. Mit diesem Update können Administratoren das Aussehen und Verhalten des Clients steuern und entscheiden, ob die lync 2013 Clientumgebung beibehalten oder die verbesserte Skype for Business-Clientumgebung verwendet werden soll. Der Skype for Business-Client hat den lync 2013-Client effektiv ersetzt und Administratoren die Möglichkeit gegeben, zwischen der vorhandenen lync-Clientumgebung und der neuen Skype for Business Clientumgebung zu wählen. Informationen zu diesem Update finden Sie unter [April 14, 2015 Update for lync 2013 (Skype for Business) (KB2889923)](https://support.microsoft.com/kb/2889923/).
  
Am 12. Mai 2015 wird ein weiteres monatliches Update von Office mit dem aktualisierten Skype for Business-Client durchgebracht. Viele Kunden, die das April-Update nicht angewendet haben, werden das 12. Mai-Update für Office 2013 abholen. Die Informationen in diesem Thema helfen Ihnen bei der Vorbereitung Ihrer Organisation, ihrer Umgebung und ihrer Benutzer auf das Client Update. Um den Übergang für Ihre Benutzer und Support Teams zu vereinfachen, verwenden Sie die Informationen in diesem Thema, um zu entscheiden, welche Clientumgebung Sie für Ihre Benutzer benötigen, und nehmen Sie dann die Änderungen an Ihrer Umgebung vor der Bereitstellung des Clientupdates in Ihrer Organisation vor.
  
- [Welche Clienterfahrung wünschen Sie für Ihre Benutzer?](user-experience.md#clientexperience)
    
- [Vorbereiten der Umgebung für den Skype for Business-Client](user-experience.md#usinglync)
    
- [Ressourcen, die Ihnen bei der Vorbereitung Ihrer Support Teams und Endbenutzer auf das Update helfen](user-experience.md#support)
    
> [!NOTE]
> Die lync 2013 Clienterfahrung ist keine Option für Skype for Business 2016-Clientversionen. Bevor Sie versuchen, ihre Clientumgebung für die Verwendung des lync 2013 Clients zu konfigurieren, überprüfen Sie die Client Version, um sicherzustellen, dass Sie nicht mit der Nummer 16 beginnt; Beispiel: 16. x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>Welche Clienterfahrung wünschen Sie für Ihre Benutzer?
<a name="clientexperience"> </a>

Mit dem neuen Skype for Business-Client können Sie steuern, welche Clientumgebung Ihre Benutzer erhalten, entweder lync oder Skype for Business. Die standardmäßige Clientumgebung hängt davon ab, ob Sie lync oder Skype for Business lokal oder Online verwenden. Wenn Sie Skype for Business Online (lync Online) heute mit Microsoft 365 apps for Enterprise, Microsoft 365 Business Standard oder Office 2013 verwenden, ist die aktualisierte Skype for Business-Clientumgebung, die von dem Aussehen und Verhalten von Skype abhängt, die Standardbenutzeroberfläche. Wenn Sie lync Server lokal heute verwenden, ist die lync-Clientumgebung die Standardeinstellung.
  
Sie können konfigurieren, welche Clientumgebung Ihre Benutzer mithilfe von Clientrichtlinien erhalten. Eine Clientrichtlinie ist eine Gruppe von Konfigurationseinstellungen, die auf Benutzer angewendet werden, wenn Sie sich bei lync oder Skype for Business anmelden.
  
### <a name="skype-for-business-client-experience"></a>Skype for Business-Clientumgebung

Zusätzlich zu allen Funktionen von lync bietet Skype for Business neue Features mit vereinfachten Steuerelementen und vertrauten Symbolen von Skype. Einige neue Features in Skype for Business sind nur mit der neuen Skype for Business-Clientumgebung verfügbar. Weitere Informationen zu den neuen Features in Skype for Business finden Sie unter [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Lync-Clientumgebung

Die lync-Clientumgebung ähnelt der lync 2013 Clienterfahrung, die Ihre Benutzer bereits kennen, aber es gibt einige Änderungen, die Sie Ihren Benutzern mitteilen sollten. Informationen zu den Unterschieden zwischen der lync-Clientumgebung und dem lync 2013-Client finden Sie unter [Warum sehe ich Skype for Business, wenn ich lync verwende?](https://go.microsoft.com/fwlink/p/?LinkId=544712) und die zusätzlichen Links weiter unten in diesem Thema.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Vorbereiten der Umgebung für den Skype for Business-Client
<a name="usinglync"> </a>

Es gibt ein paar Dinge, die Sie tun müssen, um Ihre Umgebung für das Client Update bereit zu machen. Bevor Sie mit dem vornehmen von Änderungen zum Konfigurieren der Clientumgebung beginnen, müssen Sie zunächst sicherstellen, dass Sie eine Version von Skype for Business Server oder lync Server verwenden, die die Clientrichtlinien Einstellungen unterstützt.
  
Nachdem Sie bestätigt haben, dass Sie eine Version von Skype for Business Server oder lync Server verwenden, die die Richtlinieneinstellungen zum Steuern der Clientumgebung unterstützt, müssen Sie die Richtlinieneinstellungen in Ihrer Umgebung konfigurieren. Die spezifischen Schritte, die Sie ausführen müssen, hängen von der Version von Skype for Business Server oder lync Server, die Sie verwenden, sowie davon ab, ob Ihre Benutzer lokal oder online sind. 
  
Sie sollten diese Änderungen vornehmen, bevor das Client Update an Ihre Benutzer übermittelt wird, damit Sie die Clientumgebung beim ersten Start des Skype for Business Clients steuern können. In den folgenden Tabellen werden die Schritte beschrieben, die Sie ausführen müssen, um Ihre Umgebung für die gewünschte Clientumgebung für Ihre Benutzer zu konfigurieren.
  
|**Bereitstellung**|**Skype for Business-Clientumgebung**|**Lync-Clientumgebung**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |Es gibt keine weiteren Schritte außer zum Bereitstellen des Client Builds 4711,1002 (April 2015) oder höher.  <br/> |[Verwenden der lync-Clientumgebung mit Skype for Business Online](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |Es gibt keine weiteren Schritte außer zum Bereitstellen des Client Builds 4711,1002 (April 2015) oder höher.  <br/> |[Verwenden der lync-Clientumgebung mit Skype for Business Server lokal](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 und lync Server 2010  <br/> |[Verwenden der Skype-Clientumgebung mit lync Server 2013 oder lync Server 2010 lokal](user-experience.md#SkypewithLynconprem) <br/> |[Verwenden der lync-Clientumgebung mit lync Server 2013 oder lync Server 2010 lokal](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Verwenden der Skype-Clientumgebung mit lync Server 2013 oder lync Server 2010 lokal
<a name="SkypewithLynconprem"> </a>

Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die Skype-Clientumgebung in einer lokalen Bereitstellung konfigurieren möchten. Die Standardumgebung für lokale
  
 **Schritt 1:** Stellen Sie zunächst sicher, dass Sie eine Version von lync Server ausführen, die die Clientrichtlinien Einstellungen unterstützt.
  
- **Lync Server 2013** -Sie müssen das kumulative Update vom Dezember 2014 (5.0.8308.857) für lync Server 2013 oder ein höheres Update durchführen. Weitere Informationen finden Sie unter [Updates für lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync Server 2010** -Sie müssen das kumulative Update vom Februar 2015 (4.0.7577.710) für lync Server 2010 oder ein höheres Update durchführen. Weitere Informationen finden Sie unter [Updates für lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
  **Schritt 2:** Verwenden Sie als nächstes eine Clientrichtlinie, um die Skype-Clientumgebung mit dem Skype for Business-Client festzulegen. Es gibt **drei Optionen** für die Verwendung einer Clientrichtlinie, um die Clientumgebung festzulegen.
  
  **Option 1:** Legen Sie die Skype-Clientumgebung mithilfe einer globalen Richtlinie fest. Beachten Sie, dass die globale Richtlinie auf alle Benutzer in Ihrer Bereitstellung angewendet wird, die Richtlinien auf Benutzer-und Standortebene jedoch Vorrang vor der globalen Richtlinie haben:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Option 2:** Ändern Sie eine vorhandene Clientrichtlinie, die Sie in Ihrer Umgebung verwenden, so, dass Sie die Einstellung zum Aktivieren des Skype-Client Erlebnisses enthält. Auf diese Weise können Sie die Skype-Clientumgebung nur den Benutzern zuweisen, denen die vorhandene Richtlinie zugewiesen ist:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Option 3:** Erstellen Sie eine neue Richtlinie, die Sie Benutzern zuweisen möchten, die die Einstellung für die Skype-Clientumgebung enthält. Erstellen Sie zunächst die neue Clientrichtlinie, und geben Sie den Namen der Richtlinie als Wert des Parameters **Identity** an:
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

Weisen Sie die Richtlinie dann den Benutzern zu, indem Sie den Namen der Richtlinie (den Wert, den Sie für den Parameter **Identity** verwendet haben) als Wert des Parameters **PolicyName** verwenden:
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Schritt 3:** Nachdem Sie Ihre Clientrichtlinien konfiguriert haben, stellen Sie den Skype for Business Client, Build 4711,1002 (April 2015) oder höher bereit.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Verwenden der lync-Clientumgebung mit lync Server 2013 oder lync Server 2010 lokal
<a name="LyncwithLynconprem"> </a>

Dies ist die standardmäßige Erfahrung, wenn der Skype for Business-Client in einer lokalen lync Server-Bereitstellung bereitgestellt wird. Sie müssen keine Clientrichtlinien für die Verwendung der lync-Clientumgebung konfigurieren, aber möglicherweise möchten Sie das Verhalten der ersten Ausführung für den Client steuern. Standardmäßig wird beim ersten Start des Skype for Business Clients die Skype-Clientumgebung verwendet, und Benutzern wird eine Benachrichtigung angezeigt, in der Sie aufgefordert werden, den Client neu zu starten, um die lync-Clientumgebung zu erhalten. Sie können Ihre Umgebung so konfigurieren, dass die lync-Clientumgebung angezeigt wird, wenn Benutzer den Client zum ersten Mal starten, und das Client Lernprogramm durch Ändern der Systemregistrierung auf Clientcomputern deaktivieren. Die Schritte, die Sie ausführen müssen, bevor Sie den Skype for Business-Client bereitstellen, finden Sie in einem der folgenden Themen:
  
- **Lync Server 2013**finden Sie unter [Konfigurieren der Clientumgebung mit Skype for Business in lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync Server 2010** Weitere Informationen finden Sie unter [Konfigurieren der Clientumgebung mit Skype for Business in lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Verwenden der lync-Clientumgebung mit Skype for Business Server lokal
<a name="LyncwithSfBServer"> </a>

Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die lync-Clientumgebung in einer lokalen Skype for Business Server-Bereitstellung konfigurieren möchten.
  
Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die Skype-Clientumgebung in einer lokalen Bereitstellung konfigurieren möchten. Die Standardumgebung für lokale
  
 **Schritt 1:** Stellen Sie zuerst Skype for Business Server bereit.
  
 **Schritt 2:** Verwenden Sie als nächstes eine Clientrichtlinie, um die lync-Clientumgebung mit dem Skype for Business-Client festzulegen. Es gibt **drei Optionen** für die Verwendung einer Clientrichtlinie, um die Clientumgebung festzulegen.
  
 **Option 1:** Legen Sie die lync-Clientumgebung mithilfe einer globalen Richtlinie fest. Beachten Sie, dass die globale Richtlinie auf alle Benutzer in Ihrer Bereitstellung angewendet wird, die Richtlinien auf Benutzer-und Standortebene jedoch Vorrang vor der globalen Richtlinie haben:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Option 2:** Ändern Sie eine vorhandene Clientrichtlinie, die Sie in Ihrer Umgebung verwenden, so, dass Sie die Einstellung zum Aktivieren der lync-Clientumgebung enthält. Auf diese Weise können Sie die lync-Clientumgebung nur den Benutzern zuweisen, denen die vorhandene Richtlinie zugewiesen ist:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Option 3:** Erstellen Sie eine neue Richtlinie, die Sie Benutzern zuweisen möchten, die die Einstellung für die lync-Clientumgebung enthält. Erstellen Sie zunächst die neue Clientrichtlinie, und geben Sie den Namen der Richtlinie als Wert des Parameters **Identity** an:
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

Weisen Sie die Richtlinie dann den Benutzern zu, indem Sie den Namen der Richtlinie (den Wert, den Sie für den Parameter **Identity** verwendet haben) als Wert des Parameters **PolicyName** verwenden:
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Schritt 3: optional** – Standardmäßig wird beim ersten Start des Skype for Business-Clients die Skype-Clientumgebung verwendet, und Benutzern wird eine Benachrichtigung angezeigt, in der Sie aufgefordert werden, den Client neu zu starten, um die lync-Clientumgebung zu erhalten. Sie können Ihre Umgebung so konfigurieren, dass die lync-Clientumgebung angezeigt wird, wenn Benutzer den Client zum ersten Mal starten, und das Client Lernprogramm deaktivieren, indem Sie die Systemregistrierung auf Clientcomputern ändern. Die Schritte, die Sie ausführen müssen, bevor Sie den Skype for Business-Client bereitstellen, finden Sie unter [Konfigurieren der Clientumgebung mit Skype for Business](../../deploy/deploy-clients/configure-the-client-experience.md).
  
 **Schritt 4:** Nachdem Sie Ihre Clientrichtlinien konfiguriert haben, stellen Sie den Skype for Business Client, Build 4711,1002 (April 2015) oder höher bereit.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Verwenden der lync-Clientumgebung mit Skype for Business Online
<a name="LyncwithSfBO"> </a>

Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die lync-Clientumgebung konfigurieren und Skype for Business Online verwenden möchten.
  
Wenn Sie Skype for Business Online verwenden, können Sie weiterhin die lync-Clientumgebung mit dem Skype for Business-Client in Ihrer Organisation verwenden, indem Sie mithilfe von Remote-PowerShell Clientrichtlinien konfigurieren. Es gibt **drei Optionen** für die Verwendung einer Clientrichtlinie, um die Clientumgebung festzulegen. Beachten Sie, dass sich die Richtlinien-und Parameternamen von den Einstellungen unterscheiden, die Sie zum Konfigurieren der Clientumgebung verwenden, wenn Sie Skype for Business oder lync Server lokal verwenden.
  
 **Option 1:** Legen Sie die lync-Clientumgebung mithilfe einer globalen Richtlinie fest. Beachten Sie, dass Client-und Standortrichtlinien, die auf Benutzer angewendet werden, Vorrang vor einer globalen Richtlinie haben.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 2:** Ändern Sie eine vorhandene Clientrichtlinie, die Sie in Ihrer Umgebung verwenden, so, dass Sie die Einstellung zum Aktivieren der lync-Clientumgebung enthält. Auf diese Weise können Sie die lync-Clientumgebung nur den Benutzern zuweisen, denen die vorhandene Richtlinie zugewiesen ist:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 3:** Verwenden Sie eine benutzerdefinierte Richtlinieninstanz, die die Einstellung für die lync-Clientumgebung enthält.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Nachdem Sie Ihre Clientrichtlinien konfiguriert haben, stellen Sie den Skype for Business Client, Build 4711,1002 (April 2015) oder höher bereit.
  
Ausführliche Informationen zum Konfigurieren der Clientumgebung mit Skype for Business Online, einschließlich der Schritte zum Steuern der ersten Ausführung und von PowerShell-Skripts, die Sie zum Konfigurieren Ihrer Umgebung verwenden können, finden Sie unter [Wechseln zwischen der Skype for Business und der lync-Clientbenutzeroberfläche](https://aka.ms/SfBOUI).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Ressourcen, die Ihnen bei der Vorbereitung Ihrer Support Teams und Endbenutzer auf das Update helfen
<a name="support"> </a>

Um Ihnen und Ihrer Organisation die Vorbereitung auf den Übergang zu erleichtern, stehen Ihnen viele zusätzliche Ressourcen zur Verfügung, die Ihnen bei der Planung, Aufklärung und Einbeziehung von Endbenutzern helfen.
  
- [Video: Einführung in Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype for Business schnell Start Handbücher (Download)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync ist jetzt Skype for Business – Weitere Informationen finden Sie unter What es New](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for Business: Schritt-für-Schritt-Anleitung für neue Benutzer](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Warum wird Skype for Business angezeigt, wenn ich lync verwende?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

