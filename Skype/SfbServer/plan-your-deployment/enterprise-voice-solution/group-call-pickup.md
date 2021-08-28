---
title: Planen der Gruppenanrufannahme in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Planung der Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP, wodurch Benutzer Anrufe annehmen können, die ursprünglich für andere bestimmt waren.
ms.openlocfilehash: 1127c1bb01e39d784f82dd7d451f3445f4210510
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590119"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Planen der Gruppenanrufannahme in Skype for Business
 
Planung der Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP, wodurch Benutzer Anrufe annehmen können, die ursprünglich für andere bestimmt waren.
  
Mit der Gruppenanrufannahme können Benutzer eingehende Anrufe an ihre Kollegen von ihren eigenen Telefonen aus annehmen. Dies erhöht die Verfügbarkeit der Leitung eines Benutzers, da andere Benutzer einen eingehenden Anruf durch Wählen einer Gruppennummer für die Anrufannahme annehmen können. Wenn die Gruppenanrufannahme bereitgestellt wird, kann die Anzahl der eingehenden Anrufe, die an Voicemail weitergeleitet werden, erheblich reduziert werden. Dies ist besonders nützlich für Anrufe von Kunden außerhalb Ihrer Organisation.
  
Das Feature "Gruppenanrufannahme" wurde insbesondere für Geschäftseinheiten in offenen Office-Umgebungen entwickelt. Eingehende Anrufe stören nicht, da sie nur am vorgesehenen Ziel klingeln. Andere Benutzer, die den Anruf hören, können den Anruf jedoch weiterhin annehmen, indem sie einfach die Gruppennummer wählen. 
  
In Umgebungen, in denen sich Benutzer nicht in einem offenen Office-Layout befinden oder in denen Benutzer, die eine gemeinsame Verantwortung haben, geografisch verteilt sind, stellt teamanruf die am besten geeignete Lösung dar. Der Hauptunterschied zwischen Der Gruppenanrufannahme und Teamanruf besteht darin, dass bei der Gruppenanrufannahme ein eingehender Anruf nur am vorgesehenen Ziel klingelt, aber jeder kann sich trotzdem dafür entscheiden, ihn durch Wählen einer Gruppennummer zu beantworten. Bei Einem Teamanruf klingelt der Anruf an allen Telefonen der Teammitglieder, und jeder Benutzer im Team kann das Telefon annehmen, um den Anruf entgegenzunehmen. Ein weiterer Unterschied zwischen gruppenanrufannahme und Teamanruf besteht darin, dass die Gruppenanrufannahme von einem Administrator über Skype for Business Server verwaltet wird. Bei Teamanruf verwalten Endbenutzer das Feature mithilfe des Skype for Business Clients. Mit der Gruppenanrufannahme kann daher dieser Aspekt der Anrufverwaltung zentralisiert werden.
  
Die Gruppenanrufannahme basiert auf der Anwendung zum Parken von Anrufen. Wenn Sie die Gruppenanrufannahme bereitstellen, konfigurieren Sie die Orbittabelle für das Parken von Anrufen mit separaten Bereichen von Durchwahlnummern, die als Nummern für die Anrufannahmegruppe festgelegt sind. Wie Orbitnummern für das Parken von Anrufen müssen Nummern für die Anrufannahmegruppe virtuelle Erweiterungen sein, denen kein Benutzer oder Telefon zugewiesen ist. Jeder Front-End-Pool, in dem Sie die Gruppenanrufannahme bereitstellen, kann über einen oder mehrere Bereiche von Anrufannahmegruppennummern verfügen. Die Gruppennummernbereiche müssen in der Skype for Business Server Bereitstellung global eindeutig sein. 
  
> [!NOTE]
> Nummernbereiche, die in der Orbittabelle für das Parken von Anrufen als Gruppenanrufannahmenummern festgelegt sind, können nicht mithilfe der Skype for Business Server Systemsteuerung verwaltet oder angezeigt werden. Die einzige Möglichkeit, alle Nummernbereiche in der Orbittabelle für das Parken von Anrufen anzuzeigen, besteht darin, Skype for Business Server Verwaltungsshell zu verwenden. Ebenso besteht die einzige Möglichkeit zum Hinzufügen, Ändern oder Entfernen von Nummern für die Gruppenanrufannahme darin, Skype for Business Server Verwaltungsshell zu verwenden. 
  
Nachdem Sie die Nummern für die Anrufannahmegruppe konfiguriert haben, weisen Sie einer Anrufannahmegruppe Benutzer zu. Jeder Benutzer, der einer Anrufannahmegruppe zugewiesen ist, kann seine Anrufe von anderen Benutzern beantworten lassen. Wenn ein Anruf an einen Benutzer eingeht, der einer Anrufannahmegruppe zugewiesen ist, kann jeder andere Benutzer, der den Anruf bemerkt, diesen annehmen, indem er die Nummer der Anrufannahmegruppe manuell wählt. Der Benutzer, der den Anruf entgegennimmt, muss kein Mitglied der Gruppe sein. Wenn ein Anruf von einem anderen Benutzer entgegengenommen wird, wird eine Benachrichtigung an die ursprünglich aufgerufene Nummer gesendet.
  
> [!NOTE]
> Ein Benutzer kann nur Mitglied einer Anrufannahmegruppe sein. 
  
> [!NOTE]
> Obwohl jeder Benutzer in der Skype for Business Server Bereitstellung einen Anruf an ein Mitglied einer Anrufannahmegruppe annehmen kann, muss die Person, die den Anruf annimmt, die richtige Nummer für die Anrufannahmegruppe kennen, die gewählt werden soll. 
  
Wenn ein Benutzer eine Anrufannahmegruppennummer wählt, um einen Anruf zu beantworten, wenn mehrere Telefone in der Gruppe klingeln, nimmt der Benutzer den Anruf entgegen, der am längsten klingelt.
  
Einstellungen für gleichzeitiges Klingeln funktionieren für Benutzer mit Gruppenanrufannahme. Das heißt, ein Anruf an einen Benutzer, der über die Gruppenanrufannahme verfügt, klingelt für alle konfigurierten Ziele, und ein anderer Benutzer kann den Anruf annehmen. Die Ausnahme von dieser Regel ist, wenn der Benutzer das gleichzeitige Klingeln so konfiguriert, dass alle Teammitglieder aufgerufen werden.
  
Die Gruppenanrufannahme kann nicht verwendet werden, um die folgenden Arten von Anrufen zu beantworten:
  
- Anrufe an eine Privatleitung
    
- Anrufe von einem Kontakt, dem die Datenschutzbeziehung "Freunde und Familie" zugewiesen wurde
    
    > [!TIP]
    > Ein Benutzer, der Mitglied einer Anrufannahmegruppe ist, kann verhindern, dass bestimmte Anrufe über die Gruppenanrufannahme abgerufen werden, indem er den Kontakt im Skype for Business-Client als persönlichen Kontakt markiert. Um einen Kontakt als persönlichen Kontakt zu markieren, legen Sie die Datenschutzbeziehung für den Kontakt auf Freunde und Familie fest. Eingehende Anrufe von Kontakten, deren Datenschutzbeziehung auf "Freunde und Familie" festgelegt ist, können nicht mithilfe der Gruppenanrufannahme abgerufen werden. 
  
- Videoteil von Audio-/Videoanrufen 
    
    > [!NOTE]
    > Wenn ein Benutzer einen Audio-/Videoanruf entgegennimmt, empfängt er nur die Audiodaten. Entweder die Person, die den Anruf annimmt, oder die Person, die den Anruf annimmt, kann den Anruf eskalieren, um ein Video hinzuzufügen. 
  
- Gleichzeitige Anrufe, die an Teammitglieder weitergeleitet werden
    
- Anrufe, die an einen Delegaten weitergeleitet werden
    
- Anrufe, die an eine Reaktionsgruppe weitergeleitet werden
    
Die folgenden Benutzertypen können nicht an der Gruppenanrufannahme teilnehmen. Das heißt, sie sollten nicht in eine Gruppe zur Gruppenanrufannahme einbezogen werden, und sie können keine Anrufe für Benutzer annehmen, für die die Gruppenanrufannahme aktiviert ist.
  
- Benutzer, die online in einer Hybridbereitstellung verwaltet werden
    
- Benutzer, die nicht in einem Skype for Business Server 2015-Pool oder einem Lync Server 2013-Pool mit kumulativen Updates für Lync Server 2013 verwaltet werden: Februar 2013 in einer lokalen Bereitstellung
    
Wenn niemand einen Anruf an ein Mitglied einer Anrufannahmegruppe entgegennimmt, wird der Anruf wie in den Clienteinstellungen angegeben weitergeleitet. Das heißt, der Anruf geht an Voicemail oder wird an ein anderes Ziel weitergeleitet, wie in den Clienteinstellungen angegeben.
  
## <a name="deployment-and-requirements"></a>Bereitstellung und Anforderungen

Die Gruppenanrufannahme wird automatisch bereitgestellt, wenn Sie Enterprise-VoIP und die Anwendung zum Parken von Anrufen bereitstellen. Sie aktivieren die Gruppenanrufannahme, indem Sie die Orbittabelle für das Parken von Anrufen mit separaten Nummernbereichen konfigurieren, die als Nummern für die Anrufannahmegruppe festgelegt sind, und dann Benutzern Anrufannahmegruppen zuweisen und die Benutzer für die Gruppenanrufannahme aktivieren.
  
## <a name="clients-supported-for-group-call-pickup"></a>Für die Gruppenanrufannahme unterstützte Clients

Jeder der folgenden Clients kann verwendet werden, um Anrufe an Mitglieder der Gruppenanrufannahme zu beantworten:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Benutzer können jeden dieser Clients verwenden, um Anrufe an Mitglieder der Gruppenanrufannahme zu beantworten, aber die Benutzer müssen in einem Skype for Business Server Pool oder einem Lync Server 2013-Pool mit kumulativen Updates für Lync Server 2013: Februar 2013 verwaltet werden. 
  
Die folgenden Clients und Geräte werden für die Annahme von Anrufen an Mitglieder der Gruppenanrufannahme nicht unterstützt:
  
- Lync Mobile
    
- Lync-App für Windows 8 und Windows RT
    
- Lync für iPad
    
- Analoge Telefone
    
- Telefone mit PsTN-Nummern (Public Switched Telephone Network)
    
## <a name="capacity-planning"></a>Kapazitätsplanung

In der folgenden Tabelle wird das Benutzermodell für die Gruppenanrufannahme beschrieben, das Sie als Grundlage für die Kapazitätsplanungsanforderungen verwenden können.
  
> [!IMPORTANT]
> Die Gruppenanrufannahme basiert auf der Anwendung zum Parken von Anrufen. Beachten Sie, dass bei der Kapazitätsplanung für die Notfallwiederherstellung jeder Pool eines gepaarten Pools in der Lage sein sollte, die Workloads für Anrufparkdienste, einschließlich der Gruppenanrufannahme, in beiden Pools zu verarbeiten. 
  
**Benutzermodell für die Gruppenanrufannahme**

|**Metrik**|**Pro Front-End-Pool  <br/>  (mit 8 Front-End-Servern)**|**Pro Standard Edition-Server**|
|:-----|:-----|:-----|
|Empfohlene Anzahl von Benutzern pro Gruppe  <br/> |50  <br/> |50  <br/> |
|Empfohlene Anzahl von Gruppen  <br/> |500  <br/> |60  <br/> |
|Maximale Anzahl von Benutzern pro Pool, die für die Gruppenanrufannahme aktiviert sind  <br/> |25.000  <br/> |3,000  <br/> |
|Maximale Anzahl eingehender Anrufe an alle Benutzer, die für die Gruppenanrufannahme pro Pool und Minute aktiviert sind  <br/> |500  <br/> |60  <br/> |
|Maximale Anzahl von Anrufen, die von Benutzern mit Gruppenanrufannahme pro Pool und Minute abgerufen werden  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Berechnen Sie die Metriken für Front-End-Pools mit weniger als acht Front-End-Servern linear. Wenn Ihr Front-End-Pool beispielsweise über einen Front-End-Server verfügt, berechnen Sie die maximale Last als 1/8 der in der Tabelle angezeigten Werte. 
  
> [!NOTE]
> Sie können die empfohlene Anzahl von Benutzern pro Gruppe und die Anzahl der Gruppen erhöhen oder verringern, solange Sie die maximale Anzahl von Benutzern pro Pool nicht überschreiten. Beispielsweise kann Ihr Standard Edition Server 120 Gruppen mit 25 Benutzern pro Gruppe haben, da die Anzahl der Benutzer, die für die Gruppenanrufannahme aktiviert sind, immer noch innerhalb des Maximalwerts des Benutzermodells liegt (das heißt, 120 Gruppen mal 25 Benutzer sind 3.000 Benutzer für die Gruppenanrufannahme aktiviert). 
  

