---
title: Planen der Skype for Business 2015-Clienterfahrung für Ihre Benutzer
ms.author: v-cichur
author: cichur
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
description: 'Zusammenfassung: Erfahren Sie mehr über das neue Skype for Business und die Schritte, die Sie ausführen können, um Ihre Umgebung und Ihre Benutzer auf das Update vorzubereiten, unabhängig davon, ob Sie Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015, Lync Server 2013 oder Lync Server 2010 verwenden.'
ms.openlocfilehash: 1136bcf95a0c9ee045d9947bd7a2f7771dae16fd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813925"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Planen der Skype for Business 2015-Clienterfahrung für Ihre Benutzer
 
**Zusammenfassung:** Erfahren Sie mehr über das neue Skype for Business und die Schritte, die Sie ausführen können, um Ihre Umgebung und Ihre Benutzer auf das Update vorzubereiten, unabhängig davon, ob Sie Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015, Lync Server 2013 oder Lync Server 2010 verwenden.
  
Das Office Update für Lync 2013 vom 14. April 2015 enthält die neue Skype for Business-Benutzeroberfläche. Mit diesem Update können Administratoren das Aussehen und Dasast des Clients steuern und auswählen, ob die Lync 2013-Clienterfahrung beibehalten oder die verbesserte Skype for Business-Clienterfahrung verwendet werden soll. Der Skype for Business-Client hat den Lync 2013-Client effektiv ersetzt und administratoren die Möglichkeit hinzugefügt, zwischen der vorhandenen Clienterfahrung in Lync und der neuen Skype for Business-Clienterfahrung zu wählen. Informationen zu diesem Update finden Sie im Update vom [14. April 2015 für Lync 2013 (Skype for Business) (KB2889923).](https://support.microsoft.com/kb/2889923/)
  
Am 12. Mai 2015 gibt es ein weiteres monatliches Update von Office, das den aktualisierten Skype for Business-Client enthält. Viele Kunden, die das Update vom April nicht angewendet haben, werden das Update vom 12. Mai für Office 2013 übernehmen. Die Informationen in diesem Thema helfen Ihnen bei der Vorbereitung Ihrer Organisation, Ihrer Umgebung und Ihrer Benutzer auf das Clientupdate. Um den Übergang für Ihre Benutzer und Supportteams zu erleichtern, verwenden Sie die Informationen in diesem Thema, um zu entscheiden, welche Clientumgebung Sie für Ihre Benutzer wünschen, und nehmen Sie dann die Änderungen an Ihrer Umgebung vor, bevor Sie das Clientupdate in Ihrer Organisation bereitstellen.
  
- [Welche Clienterfahrung möchten Sie für Ihre Benutzer wünschen?](user-experience.md#clientexperience)
    
- [Vorbereiten Ihrer Umgebung für den Skype for Business-Client](user-experience.md#usinglync)
    
- [Ressourcen, die Sie bei der Vorbereitung Ihrer Supportteams und Endbenutzer auf das Update unterstützen](user-experience.md#support)
    
> [!NOTE]
> Die Lync 2013-Clienterfahrung ist keine Option für Skype for Business 2016-Clientversionen. Bevor Sie versuchen, Ihre Clientumgebung für die Verwendung des Lync 2013-Clients zu konfigurieren, überprüfen Sie die Clientversion, um sicherzustellen, dass sie nicht mit der Nummer 16 beginnt. Beispiel: 16.x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>Welche Clienterfahrung möchten Sie für Ihre Benutzer wünschen?
<a name="clientexperience"> </a>

Mit dem neuen Skype for Business-Client können Sie steuern, welche Clienterfahrung Ihre Benutzer erhalten, entweder Lync oder Skype for Business. Die Standardclienterfahrung hängt davon ab, ob Sie Lync oder Skype for Business lokal oder online verwenden. Wenn Sie Skype for Business Online (Lync Online) heute mit Microsoft 365 Apps for Enterprise, Microsoft 365 Business Standard oder Office 2013 verwenden, ist die aktualisierte Skype for Business-Clientumgebung, die vom Aussehen und Aussehen von Skype inspiriert ist, die Standardbenutzeroberfläche. Wenn Sie Lync Server heute lokal verwenden, ist die Clienterfahrung in Lync die Standardeinstellung.
  
Sie können konfigurieren, welche Clienterfahrung Ihre Benutzer erhalten, indem Sie Clientrichtlinien verwenden. Eine Clientrichtlinie ist ein Satz von Konfigurationseinstellungen, die auf Benutzer angewendet werden, wenn sie sich bei Lync oder Skype for Business anmelden.
  
### <a name="skype-for-business-client-experience"></a>Skype for Business Client Experience

Zusätzlich zu allen Features von Lync bietet Skype for Business neue Funktionen mit vereinfachten Steuerelementen und vertrauten Symbolen aus Skype. Einige neue Funktionen in Skype for Business sind nur mit der neuen Skype for Business-Clienterfahrung verfügbar. Weitere Informationen zu den neuen Funktionen in Skype for Business finden Sie unter ["Skype for Business entdecken".](https://go.microsoft.com/fwlink/p/?LinkId=528686)
  
### <a name="lync-client-experience"></a>Lync-Client-Erfahrung

Die Clienterfahrung in Lync ähnelt der Lync 2013-Clientbenutzeroberfläche, mit der Ihre Benutzer bereits vertraut sind. Es gibt jedoch einige Änderungen, die Sie den Benutzern bekannt geben möchten. Informationen dazu, was sich zwischen der Lync-Client-Erfahrung und dem Lync 2013-Client unterscheiden, finden Sie unter "Warum wird [Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=544712) angezeigt, wenn ich Lync benn? " und den zusätzlichen Links weiter unten in diesem Thema."
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Vorbereiten Ihrer Umgebung für den Skype for Business-Client
<a name="usinglync"> </a>

Es gibt einige Dinge, die Sie tun müssen, um Ihre Umgebung für das Clientupdate zu bereiten. Bevor Sie änderungen an der Konfiguration der Clienterfahrung vornehmen, müssen Sie zunächst sicherstellen, dass Sie eine Version von Skype for Business Server oder Lync Server verwenden, die die Clientrichtlinieneinstellungen unterstützt.
  
Nachdem Sie bestätigt haben, dass Sie eine Version von Skype for Business Server oder Lync Server verwenden, die die Richtlinieneinstellungen zur Steuerung der Clientumgebung unterstützt, müssen Sie die Richtlinieneinstellungen in Ihrer Umgebung konfigurieren. Die spezifischen Schritte, die Sie ausführen müssen, hängen von der Version von Skype for Business Server oder Lync Server ab, die Sie verwenden, und davon, ob Ihre Benutzer lokal oder online sind. 
  
Sie sollten diese Änderungen vornehmen, bevor das Clientupdate an Ihre Benutzer übermittelt wird, damit Sie die Clienterfahrung steuern können, wenn sie den Skype for Business-Client zum ersten Mal starten. In den folgenden Tabellen werden die Schritte dargestellt, die Sie ausführen müssen, um Ihre Umgebung für die gewünschte Clientumgebung für Ihre Benutzer zu konfigurieren.
  
|**Bereitstellung**|**Skype for Business Client Experience**|**Lync-Client-Erfahrung**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |Es gibt keine weiteren Schritte als die Bereitstellung von Client build 4711.1002 (April 2015) oder höher.  <br/> |[Verwenden der Lync-Client-Erfahrung mit Skype for Business Online](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |Es gibt keine weiteren Schritte als die Bereitstellung von Client build 4711.1002 (April 2015) oder höher.  <br/> |[Verwenden der Lync-Client-Erfahrung mit lokalem Skype for Business Server](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 und Lync Server 2010  <br/> |[Verwenden der Skype-Client-Erfahrung mit Lync Server 2013 oder Lync Server 2010 (lokal)](user-experience.md#SkypewithLynconprem) <br/> |[Verwenden der Clienterfahrung in Lync Server 2013 oder Lync Server 2010 (lokal)](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Verwenden der Skype-Client-Erfahrung mit Lync Server 2013 oder Lync Server 2010 (lokal)
<a name="SkypewithLynconprem"> </a>

Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die Skype-Client-Erfahrung in einer lokalen Bereitstellung konfigurieren möchten. Die Standarderfahrung für lokale Benutzer
  
 **Schritt 1:** Stellen Sie zunächst sicher, dass Sie eine Version von Lync Server ausführen, die die Clientrichtlinieneinstellungen unterstützt.
  
- **Lync Server 2013** – Sie müssen das kumulative Update vom Dezember 2014 (5.0.8308.857) für Lync Server 2013 oder höher ausführen. Weitere Informationen finden Sie unter [Updates für Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync Server 2010** – Sie müssen das kumulative Update vom Februar 2015 (4.0.7577.710) für Lync Server 2010 oder höher ausführen. Weitere Informationen finden Sie unter [Updates für Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
  **Schritt 2:** Verwenden Sie als Nächstes eine Clientrichtlinie, um die Skype-Client-Erfahrung mit dem Skype for Business-Client zu festlegen. Es gibt **drei Optionen für** die Verwendung einer Clientrichtlinie zum Festlegen der Clienterfahrung.
  
  **Option 1:** Legen Sie die Skype-Client-Erfahrung mithilfe einer globalen Richtlinie. Beachten Sie, dass die globale Richtlinie für alle Benutzer in Ihrer Bereitstellung gilt, richtlinien auf Benutzer- und Standortebene jedoch Vorrang vor der globalen Richtlinie haben:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Option 2:** Ändern Sie eine vorhandene Clientrichtlinie, die Sie in Ihrer Umgebung verwenden, um die Einstellung zum Aktivieren der Skype-Clientumgebung zu verwenden. Auf diese Weise können Sie die Skype-Client-Erfahrung nur den Benutzern zuweisen, denen die vorhandene Richtlinie zugewiesen ist:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Option 3:** Erstellen Sie eine neue Richtlinie, die Benutzern zugewiesen werden soll, die die Einstellung für die Skype-Clienterfahrung enthält. Erstellen Sie zunächst die neue Clientrichtlinie, und geben Sie den Namen der Richtlinie als Wert für den **Parameter "Identity"** an:
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

Weisen Sie dann die Richtlinie Benutzern zu, und verwenden Sie dabei den Namen der Richtlinie (den Wert, den Sie für den **Parameter "Identity"** verwendet haben) als Wert des **Parameters "PolicyName":**
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Schritt 3:** Nachdem Sie Ihre Clientrichtlinien konfiguriert haben, stellen Sie den Skype for Business-Client, Build 4711.1002 (April, 2015) oder höher, bereitstellen.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Verwenden der Clienterfahrung in Lync Server 2013 oder Lync Server 2010 (lokal)
<a name="LyncwithLynconprem"> </a>

Dies ist die Standardeinstellung, wenn der Skype for Business-Client in einer lokalen Lync Server-Bereitstellung bereitgestellt wird. Sie müssen keine Clientrichtlinien für die Verwendung der Clientbenutzeroberfläche von Lync konfigurieren, aber Möglicherweise möchten Sie das Verhalten der ersten Ausführung für den Client steuern. Standardmäßig wird beim ersten Starten des Skype for Business-Clients die Skype-Client-Erfahrung verwendet, und Benutzern wird eine Benachrichtigung angezeigt, die anfordert, den Client neu zu starten, um die Lync-Client-Erfahrung zu erhalten. Sie können Ihre Umgebung so konfigurieren, dass die Benutzeroberfläche des Lync-Clients angezeigt wird, wenn Benutzer den Client zum ersten Mal starten, und das Clientlernprogramm deaktivieren, indem Sie die Systemregistrierung auf Clientcomputern ändern. Die Schritte, die Sie ausführen müssen, bevor Sie den Skype for Business-Client bereitstellen, finden Sie unter einem der folgenden Themen:
  
- **Lync Server 2013**, siehe ["Konfigurieren der Clienterfahrung mit Skype for Business in Lync Server 2013"](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Informationen zu Lync Server 2010** finden Sie unter ["Konfigurieren der Clienterfahrung mit Skype for Business in Lync Server 2010"](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Verwenden der Lync-Client-Erfahrung mit lokalem Skype for Business Server
<a name="LyncwithSfBServer"> </a>

Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die Lync-Client-Erfahrung in einer lokalen Skype for Business Server-Bereitstellung konfigurieren möchten.
  
Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die Skype-Client-Erfahrung in einer lokalen Bereitstellung konfigurieren möchten. Die Standarderfahrung für lokale Benutzer
  
 **Schritt 1:** Stellen Sie zunächst Skype for Business Server ein.
  
 **Schritt 2:** Verwenden Sie als Nächstes eine Clientrichtlinie, um die Clienterfahrung von Lync mit dem Skype for Business-Client zu festlegen. Es gibt **drei Optionen für** die Verwendung einer Clientrichtlinie zum Festlegen der Clienterfahrung.
  
 **Option 1:** Legen Sie die Benutzererfahrung für den Lync-Client mithilfe einer globalen Richtlinie. Beachten Sie, dass die globale Richtlinie für alle Benutzer in Ihrer Bereitstellung gilt, richtlinien auf Benutzer- und Standortebene jedoch Vorrang vor der globalen Richtlinie haben:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Option 2:** Ändern Sie eine vorhandene Clientrichtlinie, die Sie in Ihrer Umgebung verwenden, so, dass die Einstellung zum Aktivieren der Lync-Clientumgebung enthalten ist. Auf diese Weise können Sie die Clienterfahrung in Lync nur den Benutzern zuweisen, denen die vorhandene Richtlinie zugewiesen ist:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Option 3:** Erstellen Sie eine neue Richtlinie, die Benutzern zugewiesen werden soll, die die Einstellung für die Lync-Clienterfahrung enthält. Erstellen Sie zunächst die neue Clientrichtlinie, und geben Sie den Namen der Richtlinie als Wert für den **Parameter "Identity"** an:
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

Weisen Sie dann die Richtlinie Benutzern zu, und verwenden Sie dabei den Namen der Richtlinie (den Wert, den Sie für den **Parameter "Identity"** verwendet haben) als Wert des **Parameters "PolicyName":**
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Schritt 3: Optional:** Standardmäßig wird beim ersten Starten des Skype for Business-Clients die Skype-Client-Erfahrung verwendet, und benutzern wird eine Benachrichtigung angezeigt, in der sie aufgefordert werden, den Client neu zu starten, um die Benutzererfahrung des Lync-Clients zu erhalten. Sie können Ihre Umgebung so konfigurieren, dass die Benutzeroberfläche des Lync-Clients angezeigt wird, wenn Benutzer den Client zum ersten Mal starten, und das Clientlernprogramm deaktivieren, indem Sie die Systemregistrierung auf Clientcomputern ändern. Die Schritte, die Sie vor der Bereitstellung des Skype for Business-Clients ausführen müssen, finden Sie unter "Konfigurieren der [Clienterfahrung mit Skype for Business".](../../deploy/deploy-clients/configure-the-client-experience.md)
  
 **Schritt 4:** Nachdem Sie Ihre Clientrichtlinien konfiguriert haben, stellen Sie den Skype for Business-Client, Build 4711.1002 (April, 2015) oder höher, bereitstellen.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Verwenden der Lync-Client-Erfahrung mit Skype for Business Online
<a name="LyncwithSfBO"> </a>

Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die Lync-Client-Erfahrung konfigurieren und Skype for Business Online verwenden möchten.
  
Wenn Sie Skype for Business Online verwenden, können Sie weiterhin die Lync-Client-Erfahrung mit dem Skype for Business-Client in Ihrer Organisation verwenden, indem Sie Die Remote-PowerShell verwenden, um Clientrichtlinien zu konfigurieren. Es gibt **drei Optionen für** die Verwendung einer Clientrichtlinie zum Festlegen der Clienterfahrung. Beachten Sie, dass sich die Richtlinien- und Parameternamen von den Einstellungen unterscheiden, die Sie zum Konfigurieren der Clienterfahrung verwenden, wenn Sie Skype for Business oder Lync Server lokal verwenden.
  
 **Option 1:** Legen Sie die Benutzererfahrung für den Lync-Client mithilfe einer globalen Richtlinie. Beachten Sie, dass Client- und Standortrichtlinien, die auf Benutzer angewendet werden, Vorrang vor einer globalen Richtlinie haben.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 2:** Ändern Sie eine vorhandene Clientrichtlinie, die Sie in Ihrer Umgebung verwenden, so, dass die Einstellung zum Aktivieren der Lync-Clientumgebung enthalten ist. Auf diese Weise können Sie die Clienterfahrung in Lync nur den Benutzern zuweisen, denen die vorhandene Richtlinie zugewiesen ist:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 3:** Verwenden Sie eine benutzerdefinierte Richtlinieninstanz, die die Einstellung für die Clienterfahrung von Lync enthält.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Nachdem Sie Ihre Clientrichtlinien konfiguriert haben, stellen Sie den Skype for Business-Client, Build 4711.1002 (April, 2015) oder höher, bereitstellen.
  
Ausführliche Informationen zum Konfigurieren der Clientumgebung mit Skype for Business Online, einschließlich der Schritte zum Steuern der Ersten Ausführung und powerShell-Skripts, die Sie zum Konfigurieren Ihrer Umgebung verwenden können, finden Sie unter "Wechseln zwischen der [Skype for Business-](https://aka.ms/SfBOUI)und der Lync-Client-Benutzeroberfläche".
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Ressourcen, die Sie bei der Vorbereitung Ihrer Supportteams und Endbenutzer auf das Update unterstützen
<a name="support"> </a>

Um Ihnen und Ihrer Organisation die Vorbereitung auf den Übergang zu erleichtern, stehen ihnen zahlreiche zusätzliche Ressourcen zur Verfügung, die Sie bei der Planung, Schulung und Einbezieht von Endbenutzern unterstützen.
  
- [Video: Einführung in Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Schnellstarthandbücher für Skype for Business (Download)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync ist jetzt Skype for Business – erfahren Sie, was neu ist](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for Business: Schrittweise Anleitung für neue Benutzer](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Warum wird Skype for Business angezeigt, wenn ich Lync verwendet?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

