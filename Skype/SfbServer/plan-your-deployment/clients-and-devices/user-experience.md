---
title: Planen der Skype for Business-Kundenerfahrung für Ihre Benutzer
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 'Zusammenfassung: Informationen Sie zu den neuen Skype für Unternehmen und die Schritte, mit denen Sie Ihre Umgebung und Ihre Benutzer für die Aktualisierung vorbereiten, ob Sie Skype für Business Online, Skype Business Server 2015, Lync Server 2013 und Lync Server 2010 nutzen.'
ms.openlocfilehash: eaa8b7835cb3834ff9cc24a6dc941b47a2796b9f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="plan-the-skype-for-business-client-experience-for-your-users"></a>Planen der Skype for Business-Kundenerfahrung für Ihre Benutzer
 
**Zusammenfassung:** Informationen Sie zu den neuen Skype für Unternehmen und die Schritte, mit denen Sie Ihre Umgebung und Ihre Benutzer für die Aktualisierung vorbereiten, ob Sie Skype für Business Online, Skype Business Server 2015, Lync Server 2013 und Lync Server 2010 nutzen.
  
Vom 14. April 2015 Office Update für Lync 2013 enthält das neue Skype Business-Benutzeroberfläche. Dieses Update ermöglicht Administratoren das Aussehen und Verhalten des Clients zu steuern, und wählen, ob die Lync 2013-Clientumgebung beibehalten oder verwenden Sie die verbesserte Skype Business Client wünschen. Die Skype für Business Client effektiv ersetzt des Lync 2013-Clients, und die Möglichkeit für Administratoren die Auswahl zwischen den vorhandenen Lync-Clientumgebung und die neue Skype Business Client wünschen hinzugefügt. Informationen zu diesem Update finden Sie unter [14 April 2015 update für Lync 2013 (Skype für Unternehmen) (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/).
  
Am 12. Mai 2015 werden einer anderen monatliches Update Office, die die aktualisierte Skype für Business Client enthält. Viele Kunden, die nicht vom April angewendet haben Update Mai 12. übernimmt update für Office 2013. Die Informationen in diesem Thema hilft Ihnen bei der Vorbereitung Ihrer Organisation, Ihre Umgebung und Ihre Benutzer für das Clientupdate. Aktualisieren für den Übergang leicht für Ihre Benutzer und Support Teams, verwenden Sie die Informationen in diesem Thema, um Hilfe bei der Entscheidung, welcher Client treten für Ihre Benutzer verwenden möchten, und nehmen Sie die Änderungen für Ihre Umgebung vor dem Bereitstellen des Clients in Ihrer Organisation.
  
- [What client experience do you want for your users?](user-experience.md#clientexperience)
    
- [Vorbereiten der Umgebung für die Skype für Business-client](user-experience.md#usinglync)
    
- [Resources to help you prepare your support teams and your end users for the update](user-experience.md#support)
    
> [!NOTE]
> Die Lync 2013-Clientumgebung ist keine Option für Skype für Business 2016 Clientversionen. Bevor Sie versuchen, die Clientumgebung um die Verwendung des Lync 2013-Clients konfigurieren, überprüfen Sie die Clientversion, um sicherzustellen, dass es nicht mit der Nummer 16 gestartet wird; Beispiel: 16.x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>Welche Clientumgebung wünschen Sie für Ihre Benutzer?
<a name="clientexperience"> </a>

Mit der neuen Skype für Business-Client können Sie die Clientumgebung Ihre Benutzer erhalten möchten, Lync oder Skype für Business steuern. Die Default Clientbenutzeroberfläche hängt davon ab, ob Sie Lync oder Skype für Business lokal oder online arbeiten. Erleben Sie die aktualisierte Skype für Business Client bei Verwendung von Skype für Business Online (Lync Online) heute mit Office 365 ProPlus, Office 365 Business Premium oder Office 2013 – durch das Aussehen und Verhalten von Skype inspired – werden die Standard-Benutzeroberfläche. Wenn Sie Lync Server lokal heute verwenden, werden die Lync-Clientumgebung die Standardeinstellung.
  
Sie können mithilfe von Clientrichtlinien konfigurieren, welche Clientumgebung Ihre Benutzer erhalten. Eine Client-Richtlinie ist eine Gruppe von Konfigurationseinstellungen, die für Benutzer angewendet werden, wenn bei der Anmeldung an Lync oder Skype für Unternehmen.
  
### <a name="skype-for-business-client-experience"></a>Skype for Business-Clientumgebung

Zusätzlich zu den Features von Lync bietet Skype für Unternehmen neue Features mit vereinfachte-Steuerelementen und vertraute Symbole von Skype. Einige neue Features in Skype für Unternehmen stehen nur mit den neuen Skype Business Client wünschen. Weitere Informationen zu den neuen Features in Skype für Unternehmen finden Sie unter [Entdecken Skype für Unternehmen](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Lync-Clientumgebung

Die Lync-Clientumgebung ähnelt stark der Lync 2013-Clientumgebung, mit der Ihre Benutzer bereits vertraut sind, aber es gibt einige Änderungen, auf die Sie Ihre Benutzer hinweisen sollten. Um herauszufinden, was die Erfahrung Lync-Client und Lync 2013-Client unterschiedlich ist, finden Sie unter [Warum kann ich überprüfen Skype für Unternehmen, wenn ich Lync verwende?](https://go.microsoft.com/fwlink/p/?LinkId=544712) und der zusätzlichen Links weiter unten in diesem Thema.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Vorbereiten Ihrer Umgebung für den Skype for Business-Client
<a name="usinglync"> </a>

Es gibt einige Dinge, die Sie erledigen müssen, um Ihre Umgebung für das Clientupdate vorzubereiten. Bevor Sie jeder Änderung die Clientumgebung konfigurieren beginnen, müssen Sie zunächst sicherstellen, dass Sie eine Version von Skype für Business Server oder Lync Server, der die Richtlinie Clienteinstellungen unterstützt.
  
Nachdem Sie sichergestellt haben, dass Sie verwenden eine Version von Skype für Business Server oder Lync Server, der die Richtlinieneinstellungen zum Steuern der Clientumgebung unterstützt, müssen Sie die Richtlinieneinstellungen in Ihrer Umgebung konfigurieren. Die einzelnen Schritte Sie befolgen müssen hängt von der Version von Skype für Business Server oder Lync Server, die Sie verwenden, und gibt an, ob die Benutzer sind lokale oder online. 
  
Sie sollten diese Änderungen vornehmen, bevor das Clientupdate für Ihre Benutzer übermittelt werden, damit Sie die Clientumgebung aus der ersten steuern können, die Sie die Skype für Business-Client starten. In den folgenden Tabellen verweist auf die Schritte, die Sie durchführen müssen, um Ihre Umgebung für die gewünschte Clientumgebung für Ihre Benutzer konfigurieren.
  
|**Bereitstellung**|**Skype für Business-Clientumgebung**|**Lync-Clientumgebung**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |Außer der Bereitstellung von Clientbuild 4711.1002 (April 2015) oder höher gibt es keine weiteren Schritte.  <br/> |[Verwenden Sie die Lync-Client-Erfahrung mit Skype für Business Online](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |Außer der Bereitstellung von Clientbuild 4711.1002 (April 2015) oder höher gibt es keine weiteren Schritte.  <br/> |[Verwenden Sie die Lync-Client-Erfahrung mit Skype für Business Server lokal](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 und Lync Server 2010  <br/> |[Verwenden Sie die Skype-Clientumgebung mit Lync Server 2013 oder lokalen Lync Server 2010](user-experience.md#SkypewithLynconprem) <br/> |[Verwenden Sie die Lync-Client-Erfahrung mit Lync Server 2013 oder lokalen Lync Server 2010](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Verwenden Sie die Skype-Clientumgebung mit Lync Server 2013 oder lokalen Lync Server 2010
<a name="SkypewithLynconprem"> </a>

Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die Skype-Clientumgebung in einer lokalen Bereitstellung konfigurieren möchten. Dies ist die Standardumgebung für lokale Bereitstellungen.
  
 **Schritt 1:** Stellen Sie zunächst sicher, dass Sie eine Version von Lync Server ausgeführt werden, die die Richtlinie Clienteinstellungen unterstützt.
  
- **Lync Server 2013** – müssen Sie Ausführen vom Dezember 2014 kumulative Update (5.0.8308.857) für Lync Server 2013 oder einem neueren Update. Informationen finden Sie unter [Updates für Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync Server 2010** – müssen Sie Ausführen der Februar 2015 kumulative Update (4.0.7577.710) für Lync Server 2010 oder einem neueren Update. Informationen finden Sie unter [Updates für Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
 **Schritt 2:** Verwenden Sie im nächsten Schritt eine Client-Richtlinie, um die Skype-Clientumgebung mit der Skype für Business Client festzulegen. Es gibt **3 Optionen** zur Festlegung der Clientumgebung mithilfe einer Clientrichtlinie.
  
 **Option 1:** Legen Sie die Skype-Clientumgebung mithilfe einer globalen Richtlinie fest. Beachten Sie, dass die globale Richtlinie für alle Benutzer in Ihrer Bereitstellung gilt, dass Benutzer- und Standortrichtlinien jedoch Vorrang vor der globalen Richtlinie haben:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Option 2:** Ändern Sie eine vorhandene Clientrichtlinie, die Sie in Ihrer Umgebung verwenden, so ab, dass sie die Einstellung zum Aktivieren der Skype-Clientumgebung enthält. Dadurch können Sie die Skype-Clientumgebung nur für diejenigen Benutzer festlegen, denen die vorhandene Richtlinie zugewiesen ist:
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Option 3:** Erstellen Sie eine neue Richtlinie, die Sie Benutzern zuweisen und in der die Einstellung für die Skype-Clientumgebung enthalten ist. Erstellen Sie zunächst die neue Clientrichtlinie und geben Sie den Namen der Richtlinie als Wert für den Parameter **Identity** an:
  
```
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

Weisen Sie die Richtlinie dann den Benutzern zu, indem Sie den Namen der Richtlinie (den Wert, den Sie für den Parameter **Identity** verwendet haben) als Wert für den Parameter **PolicyName** verwenden:
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Schritt 3:** Nachdem Sie Ihre Clientrichtlinien konfiguriert haben, Bereitstellen der Skype für Business-Client, Build 4711.1002 (April 2015) oder höher.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Verwenden Sie die Lync-Client-Erfahrung mit Lync Server 2013 oder lokalen Lync Server 2010
<a name="LyncwithLynconprem"> </a>

Dies ist der Standard-Erfahrung bei der Bereitstellung der Skype für Business-Client in einer lokalen Lync Server-Bereitstellung. Sie müssen keine Clientrichtlinien konfigurieren, um die Lync-Clientumgebung zu verwenden, aber es kann sinnvoll sein, das Verhalten des Clients bei der ersten Ausführung zu steuern. Standardmäßig der Benutzer das erste Mal starten, der Skype für Business-Client, die Skype-Clientumgebung wird verwendet, und für Benutzer, die fordert an, dass sie den Client, um die Lync-Clients zur Verfügung neu starten wird eine Benachrichtigung angezeigt. Sie können Ihre Umgebung auch so konfigurieren, dass die Lync-Clientumgebung bereits angezeigt wird, wenn der Benutzer den Client zum ersten Mal startet, und das Clientlernprogramm deaktivieren, indem Sie die Systemregistrierung auf Clientcomputern ändern. Für die Schritte müssen Sie ausführen, vor der Bereitstellung der Skype für Business-Client finden Sie unter den folgenden Themen:
  
- **Lync Server 2013**, finden Sie unter [Konfigurieren der Clientumgebung mit Skype für Unternehmen in Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync Server 2010** finden Sie unter [Konfigurieren der Clientumgebung mit Skype für Unternehmen in Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Verwenden der Lync-Clientumgebung mit einer lokalen Bereitstellung von Skype for Business Server
<a name="LyncwithSfBServer"> </a>

Führen Sie die Schritte in diesem Abschnitt, wenn Sie die Lync-Client-Erfahrung in einer lokalen Skype für Business Server 2015 Bereitstellung konfigurieren möchten.
  
Führen Sie die Schritte in diesem Abschnitt aus, wenn Sie die Skype-Clientumgebung in einer lokalen Bereitstellung konfigurieren möchten. Dies ist die Standardumgebung für lokale Bereitstellungen.
  
 **Schritt 1:** Stellen Sie zunächst Skype für Business Server 2015 bereit.
  
 **Schritt 2:** Verwenden Sie im nächsten Schritt eine Client-Richtlinie, um die Lync-Client-Erfahrung mit der Skype für Business-Client festzulegen. Es gibt **3 Optionen** zur Festlegung der Clientumgebung mithilfe einer Clientrichtlinie.
  
 **Option 1:** Legen Sie die Lync-Clientumgebung mithilfe einer globalen Richtlinie fest. Beachten Sie, dass die globale Richtlinie für alle Benutzer in Ihrer Bereitstellung gilt, dass Benutzer- und Standortrichtlinien jedoch Vorrang vor der globalen Richtlinie haben:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Option 2:** Ändern Sie eine vorhandene Clientrichtlinie, die Sie in Ihrer Umgebung verwenden, so ab, dass sie die Einstellung zum Aktivieren der Lync-Clientumgebung enthält. Dadurch können Sie die Lync-Clientumgebung nur für diejenigen Benutzer festlegen, denen die vorhandene Richtlinie zugewiesen ist:
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Option 3:** Erstellen Sie eine neue Richtlinie, die Sie Benutzern zuweisen und in der die Einstellung für die Lync-Clientumgebung enthalten ist. Erstellen Sie zunächst die neue Clientrichtlinie und geben Sie den Namen der Richtlinie als Wert für den Parameter **Identity** an:
  
```
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

Weisen Sie die Richtlinie dann den Benutzern zu, indem Sie den Namen der Richtlinie (den Wert, den Sie für den Parameter **Identity** verwendet haben) als Wert für den Parameter **PolicyName** verwenden:
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Schritt 3: optionale** – standardmäßig, die beim ersten Starten der Skype für Business-Client, die Skype-Clientumgebung wird verwendet, und eine Benachrichtigung wird angezeigt, für Benutzer bitten, die Lync-Clients zur Verfügung, um den Client neu zu starten. Sie können Ihre Umgebung auch so konfigurieren, dass die Lync-Clientumgebung bereits angezeigt wird, wenn der Benutzer den Client zum ersten Mal startet, und das Clientlernprogramm deaktivieren, indem Sie die Systemregistrierung auf Clientcomputern ändern. Für die Schritte müssen Sie ausführen, bevor Sie die Skype für Business Client finden Sie unter [Konfigurieren der Clientumgebung mit Skype für Unternehmen](../../deploy/deploy-clients/configure-the-client-experience.md)bereitstellen.
  
 **Schritt 4:** Nachdem Sie Ihre Clientrichtlinien konfiguriert haben, Bereitstellen der Skype für Business-Client, Build 4711.1002 (April 2015) oder höher.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Verwenden der Lync-Clientumgebung mit Skype for Business Online
<a name="LyncwithSfBO"> </a>

Führen Sie die Schritte in diesem Abschnitt, wenn Sie die Lync-Clientumgebung und Skype für Business Online verwenden Sie konfigurieren möchten.
  
Bei Verwendung von Skype für Business Online dennoch können die Lync-Client-Erfahrung mit der Skype für Business-Client in Ihrer Organisation Sie mithilfe von Remote-PowerShell zum Konfigurieren von Clientrichtlinien. Es gibt **3 Optionen** zur Festlegung der Clientumgebung mithilfe einer Clientrichtlinie. Beachten Sie, dass die Namen der Richtlinie und Parameter anders als die Einstellungen, mit denen Sie die Client-Erfahrung bei Verwendung der Skype für Geschäftskunden und Lync Server Konfigurieren lokaler.
  
 **Option 1:** Die Lync-Clientumgebung mithilfe einer globalen Richtlinie festgelegt. Beachten Sie, dass die Client- und Website-Richtlinien auf Benutzer angewendet werden eine globale Richtlinie Vorrang vor haben.
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 2:** Ändern Sie eine vorhandene Clientrichtlinie, die Sie in Ihrer Umgebung verwenden, so ab, dass sie die Einstellung zum Aktivieren der Lync-Clientumgebung enthält. Dadurch können Sie die Lync-Clientumgebung nur für diejenigen Benutzer festlegen, denen die vorhandene Richtlinie zugewiesen ist:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Option 3:** Verwenden Sie eine benutzerdefinierte Richtlinie-Instanz, die die Einstellung für die Lync-Clientumgebung enthält.
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Nachdem Sie Ihre Clientrichtlinien konfiguriert haben, Bereitstellen der Skype für Business-Client, Build 4711.1002 (April 2015) oder höher.
  
Ausführliche Informationen zum Konfigurieren des Clients von Erfahrung mit Skype Business Online, einschließlich Informationen zum Steuern des ersten Textlauf Erfahrung und PowerShell-Skripts Sie Ihre Umgebung konfigurieren können, finden Sie unter [Umschalten zwischen der Skype für Unternehmen und die Lync-Client-Benutzeroberflächen](https://aka.ms/SfBOUI).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Ressourcen zur besseren Vorbereitung Ihrer Supportteams und Endbenutzer auf das Update
<a name="support"> </a>

Wir haben, damit es einfacher für Sie und Ihre Organisation für den Übergang vorbereiten, viele zusätzliche Ressourcen zur Verfügung, mit denen Sie planen, informieren und ausschließlich für Endbenutzer zu.
  
- [Video: Einführung in Skype für Unternehmen](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype für Business Schnellstart-Handbuch (Download)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync ist nun Skype für Unternehmen – finden Sie unter Neuigkeiten](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype für Unternehmen: schrittweise Anleitung für neue Benutzer](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Warum werden ich Skype für Unternehmen angezeigt, wenn ich Lync verwende?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

