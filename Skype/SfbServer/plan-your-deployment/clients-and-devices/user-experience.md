---
title: Planen der Skype for Business 2015-Clientumgebung für Ihre Benutzer
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 'Zusammenfassung: Erfahren Sie mehr über die neuen Skype for Business und die Schritte, die Sie ausführen können, um Ihre Umgebung und Ihre Benutzer auf das Update vorzubereiten, unabhängig davon, ob Sie Skype for Business Online, Skype for Business Server 2019, Skype for Business Server  2015, Lync Server 2013 oder Lync Server 2010.'
---

# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Planen der Skype for Business 2015-Clientumgebung für Ihre Benutzer
 
**Zusammenfassung:** Erfahren Sie mehr über die neuen Skype for Business und die Schritte, die Sie ausführen können, um Ihre Umgebung und Ihre Benutzer auf das Update vorzubereiten, unabhängig davon, ob Sie Skype for Business Online Skype for Business Server 2019 Skype for Business Server  2015, Lync Server 2013 oder Lync Server 2010.
  
Das Office Update für Lync 2013 vom 14. April 2015 enthält die neue Skype for Business Benutzeroberfläche. Mit diesem Update können Administratoren das Aussehen und Verhalten des Clients steuern und auswählen, ob die Lync 2013-Clientumgebung beibehalten oder die verbesserte Skype for Business Clientumgebung verwendet werden soll. Der Skype for Business-Client hat den Lync 2013-Client effektiv ersetzt und Administratoren die Möglichkeit hinzugefügt, zwischen der vorhandenen Lync-Clientumgebung und der neuen Skype for Business Clientumgebung zu wählen. Informationen zu diesem Update finden Sie im [Update vom 14. April 2015 für Lync 2013 (Skype for Business) (KB2889923).](https://support.microsoft.com/kb/2889923/).
  
Am 12. Mai 2015 gibt es ein weiteres monatliches Update von Office, das den aktualisierten Skype for Business-Client enthält. Viele Kunden, die das April-Update nicht angewendet haben, nehmen das Update vom 12. Mai für Office 2013 auf. Die Informationen in diesem Thema helfen Ihnen, Ihre Organisation, Ihre Umgebung und Ihre Benutzer auf das Clientupdate vorzubereiten. Um den Übergang für Ihre Benutzer und Supportteams zu vereinfachen, verwenden Sie die Informationen in diesem Thema, um zu entscheiden, welche Clientumgebung Sie für Ihre Benutzer wünschen, und nehmen Sie dann die Änderungen an Ihrer Umgebung vor der Bereitstellung des Clientupdates in Ihrer Organisation vor.
  
- [Welche Clientumgebung möchten Sie für Ihre Benutzer?](user-experience.md#clientexperience)
    
- [Vorbereiten der Umgebung für den Skype for Business-Client](user-experience.md#usinglync)
    
- [Ressourcen, mit denen Sie Ihre Supportteams und Ihre Endbenutzer auf das Update vorbereiten können](user-experience.md#support)
    
> [!NOTE]
> Die Lync 2013-Clientumgebung ist keine Option für Skype for Business 2016-Clientversionen. Bevor Sie versuchen, Ihre Clientumgebung für die Verwendung des Lync 2013-Clients zu konfigurieren, überprüfen Sie die Clientversion, um sicherzustellen, dass sie nicht mit der Nummer 16 beginnt. Beispiel: 16.x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>Welche Clientumgebung möchten Sie für Ihre Benutzer?
<a name="clientexperience"> </a>

Mit dem neuen Skype for Business-Client können Sie steuern, welche Clientumgebung Ihre Benutzer erhalten, entweder Lync oder Skype for Business. Die Standardclientumgebung hängt davon ab, ob Sie Lync oder Skype for Business lokal oder online verwenden. Wenn Sie Skype for Business Online (Lync Online) heute mit Microsoft 365 Apps for Enterprise, Microsoft 365 Business Standard oder Office 2013 verwenden, wird die aktualisierte Skype for Business  Die Clientumgebung , die vom Aussehen und Verhalten von Skype inspiriert ist, ist die Standard-Benutzeroberfläche. Wenn Sie lync Server heute lokal verwenden, ist die Lync-Clientumgebung die Standardeinstellung.
  
Mithilfe von Clientrichtlinien können Sie konfigurieren, welche Clientumgebung Ihre Benutzer erhalten. Eine Clientrichtlinie ist eine Reihe von Konfigurationseinstellungen, die auf Benutzer angewendet werden, wenn sie sich bei Lync oder Skype for Business anmelden.
  
### <a name="skype-for-business-client-experience"></a>Skype for Business Clientumgebung

Zusätzlich zu allen Features von Lync bietet Skype for Business neue Features mit vereinfachten Steuerelementen und vertrauten Symbolen aus Skype. Einige neue Features in Skype for Business sind nur mit dem neuen Skype for Business Client verfügbar. Weitere Informationen zu den neuen Features in Skype for Business finden Sie unter ["Entdecken Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686)".
  
### <a name="lync-client-experience"></a>Lync-Clientumgebung

Die Lync-Clientumgebung ist der Lync 2013-Clientumgebung, mit der Ihre Benutzer bereits vertraut sind, sehr ähnlich, aber es gibt einige Änderungen, über die Sie Ihre Benutzer informieren möchten. Informationen dazu, was sich zwischen der Lync-Clientumgebung und dem Lync 2013-Client unterscheidet, finden Sie unter ["Warum werden Skype for Business angezeigt, wenn ich Lync verwende?"](https://go.microsoft.com/fwlink/p/?LinkId=544712) und die zusätzlichen Links weiter unten in diesem Thema.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Vorbereiten der Umgebung für den Skype for Business-Client
<a name="usinglync"> </a>

Es gibt einige Dinge, die Sie tun müssen, um Ihre Umgebung für das Clientupdate vorzubereiten. Bevor Sie mit änderungen an der Konfiguration der Clientumgebung beginnen, müssen Sie zunächst sicherstellen, dass Sie eine Version von Skype for Business Server oder Lync Server verwenden, die die Clientrichtlinieneinstellungen unterstützt.
  
Nachdem Sie bestätigt haben, dass Sie eine Version von Skype for Business Server oder Lync Server verwenden, die die Richtlinieneinstellungen zum Steuern der Clientumgebung unterstützt, müssen Sie die Richtlinieneinstellungen in Ihrer Umgebung konfigurieren. Welche Schritte Sie ausführen müssen, hängt von der Version von Skype for Business Server oder Lync Server ab, die Sie verwenden, und davon, ob Ihre Benutzer lokal oder online sind. 
  
Sie sollten diese Änderungen vornehmen, bevor das Clientupdate an Ihre Benutzer übermittelt wird, damit Sie die Clientumgebung ab dem ersten Start des Skype for Business Clients steuern können. In den folgenden Tabellen sind die Schritte aufgeführt, die Sie ausführen müssen, um Ihre Umgebung für die gewünschte Clientumgebung für Ihre Benutzer zu konfigurieren.
  
|**Bereitstellung**|**Skype for Business Clientumgebung**|**Lync-Clientumgebung**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |Außer der Bereitstellung von Clientbuild 4711.1002 (April 2015) oder höher gibt es keine weiteren Schritte.  <br/> |[Verwenden der Lync-Clientumgebung mit Skype for Business Online](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |Außer der Bereitstellung von Clientbuild 4711.1002 (April 2015) oder höher gibt es keine weiteren Schritte.  <br/> |[Verwenden der Lync-Clientumgebung mit Skype for Business Server lokal](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 und Lync Server 2010  <br/> |[Verwenden der Skype Clientumgebung mit lync Server 2013 oder lokalen Lync Server 2010](user-experience.md#SkypewithLynconprem) <br/> |[Verwenden der Lync-Clientumgebung mit lync Server 2013 oder lync Server 2010 lokal](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Verwenden der Skype Clientumgebung mit lync Server 2013 oder lokalen Lync Server 2010
<a name="SkypewithLynconprem"> </a>

Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die Skype Clientumgebung in einer lokalen Bereitstellung konfigurieren möchten. Die Standardumgebung für lokale Bereitstellungen
  
 **Schritt 1:** Stellen Sie zunächst sicher, dass Sie eine Version von Lync Server ausführen, die die Clientrichtlinieneinstellungen unterstützt.
  
- **Lync Server 2013** – Sie müssen das kumulative Update vom Dezember 2014 (5.0.8308.857) für Lync Server 2013 oder ein späteres Update ausführen. Weitere Informationen finden Sie unter [Updates für Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync Server 2010** – Sie müssen das kumulative Update vom Februar 2015 (4.0.7577.710) für Lync Server 2010 oder ein späteres Update ausführen. Weitere Informationen finden Sie unter [Updates für Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
  **Schritt 2:** Verwenden Sie als Nächstes eine Clientrichtlinie, um die Skype Clientumgebung mit dem Skype for Business-Client festzulegen. Es gibt **drei Optionen** für die Verwendung einer Clientrichtlinie, um die Clientumgebung festzulegen.
  
  **Option 1:** Legen Sie die Skype Clientumgebung mithilfe einer globalen Richtlinie fest. Beachten Sie, dass die globale Richtlinie für alle Benutzer in Ihrer Bereitstellung gilt, richtlinien auf Benutzer- und Standortebene jedoch Vorrang vor der globalen Richtlinie haben:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Option 2:** Ändern Sie eine vorhandene Clientrichtlinie, die Sie in Ihrer Umgebung verwenden, so, dass sie die Einstellung enthält, um die Skype Clientumgebung zu aktivieren. Auf diese Weise können Sie die Skype Clientumgebung nur den Benutzern zuweisen, denen die vorhandene Richtlinie zugewiesen ist:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Option 3:** Erstellen Sie eine neue Richtlinie, die Benutzern zugewiesen werden soll, die die Einstellung für die Skype Clientumgebung enthält. Erstellen Sie zunächst die neue Clientrichtlinie, und geben Sie den Namen der Richtlinie als Wert des **Parameters "Identity"** an:
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

Weisen Sie die Richtlinie dann Benutzern zu, indem Sie den Namen der Richtlinie (den Wert, den Sie für den **Parameter Identity** verwendet haben) als Wert des **PolicyName-Parameters** verwenden:
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Schritt 3:** Nachdem Sie Ihre Clientrichtlinien konfiguriert haben, stellen Sie den Skype for Business Client, Build 4711.1002 (April 2015) oder höher bereit.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Verwenden der Lync-Clientumgebung mit lync Server 2013 oder lync Server 2010 lokal
<a name="LyncwithLynconprem"> </a>

Dies ist die Standardumgebung, wenn der Skype for Business-Client in einer lokalen Lync Server-Bereitstellung bereitgestellt wird. Sie müssen keine Clientrichtlinien konfigurieren, um die Lync-Clientumgebung zu verwenden, aber Sie können das Verhalten bei der ersten Ausführung für den Client steuern. Wenn Benutzer den Skype for Business Client zum ersten Mal starten, wird standardmäßig die Skype Clientoberfläche verwendet, und Benutzern wird eine Benachrichtigung angezeigt, die anfordert, dass sie den Client neu starten, um die Lync-Clientumgebung zu erhalten. Sie können Ihre Umgebung so konfigurieren, dass die Lync-Clientumgebung angezeigt wird, wenn Benutzer den Client zum ersten Mal starten, und das Clientlernprogramm deaktivieren, indem Sie die Systemregistrierung auf Clientcomputern ändern. Die Schritte, die Sie vor der Bereitstellung des Skype for Business-Clients ausführen müssen, finden Sie in einem der folgenden Themen:
  
- **Lync Server 2013**: [Konfigurieren der Clientumgebung mit Skype for Business in Lync Server 2013](/previous-versions/office/lync-server-2013/configure-the-skype-for-business-client-in-lync-server-2013)
    
- **Lync Server 2010** siehe [Konfigurieren der Clientumgebung mit Skype for Business in Lync Server 2010](/previous-versions/office/skype-server-2010/dn955209(v=ocs.14))
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Verwenden der Lync-Clientumgebung mit Skype for Business Server lokal
<a name="LyncwithSfBServer"> </a>

Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die Lync-Clientumgebung in einer lokalen Skype for Business Server-Bereitstellung konfigurieren möchten.
  
Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die Skype Clientumgebung in einer lokalen Bereitstellung konfigurieren möchten. Die Standardumgebung für lokale Bereitstellungen
  
 **Schritt 1:** Stellen Sie zunächst Skype for Business Server bereit.
  
 **Schritt 2:** Verwenden Sie als Nächstes eine Clientrichtlinie, um die Lync-Clientumgebung mit dem Skype for Business-Client festzulegen. Es gibt **drei Optionen** für die Verwendung einer Clientrichtlinie, um die Clientumgebung festzulegen.
  
 **Option 1:** Legen Sie die Lync-Clientumgebung mithilfe einer globalen Richtlinie fest. Beachten Sie, dass die globale Richtlinie für alle Benutzer in Ihrer Bereitstellung gilt, richtlinien auf Benutzer- und Standortebene jedoch Vorrang vor der globalen Richtlinie haben:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Option 2:** Ändern Sie eine vorhandene Clientrichtlinie, die Sie in Ihrer Umgebung verwenden, so, dass sie die Einstellung zum Aktivieren der Lync-Clientumgebung enthält. Auf diese Weise können Sie die Lync-Clientumgebung nur den Benutzern zuweisen, denen die vorhandene Richtlinie zugewiesen ist:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Option 3:** Erstellen Sie eine neue Richtlinie, die Benutzern zugewiesen werden soll, die die Einstellung für die Lync-Clientumgebung enthält. Erstellen Sie zunächst die neue Clientrichtlinie, und geben Sie den Namen der Richtlinie als Wert des **Parameters "Identity"** an:
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

Weisen Sie die Richtlinie dann Benutzern zu, indem Sie den Namen der Richtlinie (den Wert, den Sie für den **Parameter Identity** verwendet haben) als Wert des **PolicyName-Parameters** verwenden:
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Schritt 3: Optional–** Wenn Benutzer den Skype for Business Client zum ersten Mal starten, wird standardmäßig die Skype Clientumgebung verwendet, und benutzern wird eine Benachrichtigung angezeigt, in der sie aufgefordert werden, den Client neu zu starten, um die Lync-Clientumgebung zu erhalten. Sie können Ihre Umgebung so konfigurieren, dass die Lync-Clientumgebung angezeigt wird, wenn Benutzer den Client zum ersten Mal starten, und das Clientlernprogramm deaktivieren, indem Sie die Systemregistrierung auf Clientcomputern ändern. Die Schritte, die Sie ausführen müssen, bevor Sie den Skype for Business-Client bereitstellen, finden Sie unter [Konfigurieren der Clientumgebung mit Skype for Business](../../deploy/deploy-clients/configure-the-client-experience.md).
  
 **Schritt 4:** Nachdem Sie Ihre Clientrichtlinien konfiguriert haben, stellen Sie den Skype for Business Client, Build 4711.1002 (April 2015) oder höher bereit.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Verwenden der Lync-Clientumgebung mit Skype for Business Online
<a name="LyncwithSfBO"> </a>

Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die Lync-Clientumgebung konfigurieren und Skype for Business Online verwenden möchten.
  
Wenn Sie Skype for Business Online verwenden, können Sie weiterhin die Lync-Clientumgebung mit dem Skype for Business-Client in Ihrer Organisation verwenden, indem Sie Remote-PowerShell verwenden, um Clientrichtlinien zu konfigurieren. Es gibt **drei Optionen** für die Verwendung einer Clientrichtlinie, um die Clientumgebung festzulegen. Beachten Sie, dass sich die Richtlinien- und Parameternamen von den Einstellungen unterscheiden, die Sie zum Konfigurieren der Clientumgebung verwenden, wenn Sie Skype for Business oder lync Server lokal verwenden.
  
 **Option 1:** Legen Sie die Lync-Clientumgebung mithilfe einer globalen Richtlinie fest. Beachten Sie, dass Client- und Standortrichtlinien, die auf Benutzer angewendet werden, Vorrang vor einer globalen Richtlinie haben.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 2:** Ändern Sie eine vorhandene Clientrichtlinie, die Sie in Ihrer Umgebung verwenden, so, dass sie die Einstellung zum Aktivieren der Lync-Clientumgebung enthält. Auf diese Weise können Sie die Lync-Clientumgebung nur den Benutzern zuweisen, denen die vorhandene Richtlinie zugewiesen ist:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 3:** Verwenden Sie eine benutzerdefinierte Richtlinieninstanz, die die Einstellung für die Lync-Clientumgebung enthält.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Nachdem Sie Ihre Clientrichtlinien konfiguriert haben, stellen Sie den Skype for Business Client, Build 4711.1002 (April 2015) oder höher bereit.
  
Ausführliche Informationen zum Konfigurieren der Clientumgebung mit Skype for Business Online, einschließlich Der Schritte zum Steuern der Ersten Ausführung und PowerShell-Skripts, die Sie zum Konfigurieren Ihrer Umgebung verwenden können, finden Sie unter [Wechseln zwischen der Skype for Business und den Lync-Clientbenutzeroberflächen](../../../SfbOnline/set-up-skype-for-business-online/switching-the-skype-for-business-and-the-lync-client-user-interfaces.md).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Ressourcen, mit denen Sie Ihre Supportteams und Ihre Endbenutzer auf das Update vorbereiten können
<a name="support"> </a>

Um Ihnen und Ihrer Organisation die Vorbereitung auf den Übergang zu erleichtern, stehen viele zusätzliche Ressourcen zur Verfügung, die Ihnen bei der Planung, Schulung und Einbindung von Endbenutzern helfen.
  
- [Video: Einführung in Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype for Business Schnellstartanleitungen (Download)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync ist jetzt Skype for Business – Neuigkeiten anzeigen](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for Business: Schrittweise Anleitung für neue Benutzer](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Warum wird Skype for Business angezeigt, wenn ich Lync verwende?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
