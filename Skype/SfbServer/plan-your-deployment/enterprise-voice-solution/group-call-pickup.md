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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Planung der Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP, mit der Benutzer Anrufe beantworten können, die ursprünglich für andere bestimmt waren.
ms.openlocfilehash: 874b9385352a8c51d9c9a356dd0ccc2ca3070601
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825615"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Planen der Gruppenanrufannahme in Skype for Business
 
Planung der Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP, mit der Benutzer Anrufe beantworten können, die ursprünglich für andere bestimmt waren.
  
Mit der Gruppenanrufannahme können Benutzer eingehende Anrufe an kollegen von ihren eigenen Telefonen aus entgegennahmen. Dadurch wird die Verfügbarkeit der Leitung eines Benutzers erhöht, da andere Benutzer einen eingehenden Anruf beantworten können, indem sie eine Gruppennummer für die Anrufannahme wählen. Wenn die Gruppenanrufannahme bereitgestellt wird, kann die Anzahl eingehender Anrufe, die an Voicemail geroutet werden, erheblich reduziert werden. Dies ist besonders hilfreich für Anrufe von Kunden außerhalb Ihrer Organisation.
  
Die Funktion "Gruppenanrufannahme" ist insbesondere für Geschäftseinheiten in offenen Büroumgebungen konzipiert. Eingehende Anrufe stören nicht, da sie nur am vorgesehenen Ziel klingeln. Andere Benutzer, die das Klingeln hören, können den Anruf jedoch trotzdem einfach durch Wählen der Gruppennummer an sich nehmen. 
  
In Umgebungen, in denen sich Benutzer nicht in einem offenen Bürolayout befinden oder benutzer, die eine gemeinsame Verantwortung teilen, geografisch verteilt sind, stellt der Teamanruf die am besten geeignete Lösung dar. Der Hauptunterschied zwischen Gruppenanrufannahme und Teamanruf besteht in dem Unterschied, dass bei der Gruppenanrufannahme ein eingehender Anruf nur am vorgesehenen Ziel klingelt, aber dennoch jeder wählen kann, ob er eine Gruppennummer wählt. Beim Teamanruf klingelt der Anruf an allen Telefonen der Teammitglieder, und jeder Benutzer im Team kann das Telefon zum Beantworten des Anrufs an sich nehmen. Ein weiterer Unterschied zwischen gruppenanrufannahme und Teamanruf ist, dass die Gruppenanrufannahme von einem Administrator über Skype for Business Server verwaltet wird. Bei Teamanrufen verwalten Endbenutzer die Funktion mithilfe des Skype for Business-Clients. Mit der Gruppenanrufannahme kann daher dieser Aspekt der Anrufverwaltung zentralisiert werden.
  
Die Gruppenanrufannahme baut auf der Anwendung zum Parken von Anrufen auf. Wenn Sie die Gruppenanrufannahme bereitstellen, konfigurieren Sie die Orbittabelle für das Parken von Anrufen mit separaten Durchwahlnummernbereichen, die als Gruppennummern für die Anrufannahme festgelegt sind. Wie Orbitnummern zum Parken von Anrufen müssen Nummern der Anrufannahmegruppe virtuelle Durchstellen sein, denen kein Benutzer oder Telefon zugewiesen ist. Jeder Front-End-Pool, in dem Sie die Gruppenanrufannahme bereitstellen, kann einen oder mehrere Bereiche von Gruppennummern für die Anrufannahme enthalten. Die Gruppennummerbereiche müssen global innerhalb der Skype for Business Server-Bereitstellung eindeutig sein. 
  
> [!NOTE]
> Nummernbereiche, die in der Orbittabelle zum Parken von Anrufen als Gruppenanrufannahmenummern festgelegt sind, können nicht mithilfe der Skype for Business Server-Systemsteuerung verwaltet oder angezeigt werden. Die einzige Möglichkeit, alle Nummernbereiche in der Orbittabelle zum Parken von Anrufen zu sehen, ist die Verwendung der Skype for Business Server-Verwaltungsshell. Ebenso besteht die einzige Möglichkeit zum Hinzufügen, Ändern oder Entfernen von Gruppenanrufannahmenummern in der Verwendung der Skype for Business Server-Verwaltungsshell. 
  
Nachdem Sie die Nummern der Anrufannahmegruppe konfiguriert haben, weisen Sie einer Anrufannahmegruppe Benutzer zu. Jeder Benutzer, der einer Anrufannahmegruppe zugewiesen ist, kann seine Anrufe von anderen Benutzern beantworten lassen. Wenn ein Anruf bei einem Benutzer einkommt, der einer Anrufannahmegruppe zugewiesen ist, kann jeder andere Benutzer, der den Anruf bemerkt, ihn durch manuelles Wählen der Nummer der Anrufannahmegruppe beantworten. Der Benutzer, der den Anruf an nimmt, muss kein Mitglied der Gruppe sein. Wenn ein Anruf von einem anderen Benutzer abgeholt wird, wird eine Benachrichtigung an die ursprünglich angerufene Nummer gesendet.
  
> [!NOTE]
> Ein Benutzer kann nur Mitglied einer Einzigen Anrufannahmegruppe sein. 
  
> [!NOTE]
> Obwohl jeder Benutzer in der Skype for Business Server-Bereitstellung einen Anruf an ein Mitglied der Anrufannahmegruppe beantworten kann, muss die Person, die den Anruf anwählt, die richtige Nummer für die Anrufannahmegruppe kennen. 
  
Wenn ein Benutzer eine Nummer einer Anrufannahmegruppe wählt, um einen Anruf zu beantworten, wenn mehrere Telefone in der Gruppe klingeln, beantwortet der Benutzer den Anruf, der am längsten klingelt.
  
Einstellungen für gleichzeitiges Klingeln funktionieren für Benutzer mit Gruppenanrufannahme. Das heißt, ein Anruf, der an einen Benutzer mit Gruppenanrufannahme erfolgt, klingelt für alle konfigurierten Ziele, und ein anderer Benutzer kann den Anruf beantworten. Die Ausnahme von dieser Regel ist, wenn der Benutzer gleichzeitiges Klingeln so konfiguriert, dass alle Teammitglieder anrufen.
  
Die Gruppenanrufannahme kann nicht zum Beantworten der folgenden Anruftypen verwendet werden:
  
- Anrufe an eine Privatleitung
    
- Anrufe von einem Kontakt, dem die Datenschutzbeziehung "Freunde und Familie" zugewiesen wurde
    
    > [!TIP]
    > Ein Benutzer, der Mitglied einer Anrufannahmegruppe ist, kann verhindern, dass bestimmte Anrufe über die Gruppenanrufannahme abgerufen werden, indem er den Kontakt im Skype for Business-Client als persönlichen Kontakt markiert. Um einen Kontakt als persönlichen Kontakt zu markieren, legen Sie die Datenschutzbeziehung für den Kontakt auf "Freunde und Familie" festgelegt. Alle eingehenden Anrufe von Kontakten, deren Datenschutzbeziehung auf "Freunde und Familie" festgelegt ist, können nicht mithilfe der Gruppenanrufannahme abgerufen werden. 
  
- Videoteil von Audio-/Videoanrufen 
    
    > [!NOTE]
    > Wenn ein Benutzer einen Audio-/Videoanruf beantwortet, erhält er nur die Audiodaten. Entweder die Person, die anruft, oder die Person, die den Anruf beantwortet, kann den Anruf eskalieren, um Video hinzuzufügen. 
  
- Gleichzeitiges Klingeln von Anrufen, die an Teammitglieder geroutet werden
    
- Anrufe, die an eine Stellvertretung geroutet werden
    
- Anrufe, die an eine Reaktionsgruppe geroutet werden
    
Die folgenden Benutzertypen können nicht an der Gruppenanrufannahme teilnehmen. Das heißt, sie sollten nicht in eine Gruppenanrufannahmegruppe aufgenommen werden, und sie können keine Anrufe für Benutzer mit aktivierter Gruppenanrufannahme an sich nehmen.
  
- Benutzer, die online in einer Hybridbereitstellung zu Hause sind
    
- Benutzer, die nicht in einem Skype for Business Server 2015-Pool oder einem Lync Server 2013-Pool mit kumulativen Updates für Lync Server 2013 gespeichert sind: Februar 2013 in einer lokalen Bereitstellung
    
Wenn kein Benutzer einen Anruf an ein Mitglied einer Anrufannahmegruppe beantwortet, wird der Anruf wie in den Clienteinstellungen angegeben geroutet. Das heißt, der Anruf wird an die Voicemail oder an ein anderes Ziel weitergeleitet, wie in den Clienteinstellungen angegeben.
  
## <a name="deployment-and-requirements"></a>Bereitstellung und Anforderungen

Die Gruppenanrufannahme wird automatisch bereitgestellt, wenn Sie Enterprise-VoIP und die Anwendung zum Parken von Anrufen bereitstellen. Sie aktivieren die Gruppenanrufannahme, indem Sie die Orbittabelle für das Parken von Anrufen mit separaten Nummernbereichen konfigurieren, die als Gruppennummern für die Anrufannahme festgelegt sind, und anschließend Benutzer Anrufannahmegruppen zuweisen und die Benutzer für die Gruppenanrufannahme aktivieren.
  
## <a name="clients-supported-for-group-call-pickup"></a>Für die Gruppenanrufannahme unterstützte Clients

Jeder der folgenden Clients kann verwendet werden, um Anrufe an Mitglieder der Gruppenanrufannahme zu beantworten:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Benutzer können jeden dieser Clients verwenden, um Anrufe an Mitglieder der Gruppenanrufannahme zu beantworten. Die Benutzer müssen jedoch in einem Skype for Business Server-Pool oder einem Lync Server 2013-Pool mit kumulativen Updates für Lync Server 2013, Februar 2013, gespeichert sein. 
  
Die folgenden Clients und Geräte werden nicht für das Aufnehmen von Anrufen an Gruppenanrufannahmemitglieder unterstützt:
  
- Lync Mobile
    
- Lync-App für Windows 8 und Windows RT
    
- Lync für iPad
    
- Analoge Telefone
    
- Telefone mit Festnetznummern (Public Switched Telephone Network, PSTN)
    
## <a name="capacity-planning"></a>Kapazitätsplanung

In der folgenden Tabelle wird das Benutzermodell für die Gruppenanrufannahme beschrieben, das Sie als Grundlage für die Kapazitätsplanungsanforderungen verwenden können.
  
> [!IMPORTANT]
> Die Gruppenanrufannahme basiert auf der Anwendung zum Parken von Anrufen. Beachten Sie, dass bei der Kapazitätsplanung für die Notfallwiederherstellung jeder Pool eines gekoppelten Pools in der Lage sein sollte, die Arbeitsauslastungen für Die Anrufparkdienste, einschließlich der Gruppenanrufannahme, in beiden Pools zu verarbeiten. 
  
**Benutzermodell für die Gruppenanrufannahme**

|**Metrik**|**Pro Front-End-Pool  <br/>  (mit 8 Front-End-Servern)**|**Pro Standard Edition-Server**|
|:-----|:-----|:-----|
|Empfohlene Anzahl von Benutzern pro Gruppe  <br/> |50  <br/> |50  <br/> |
|Empfohlene Anzahl von Gruppen  <br/> |500  <br/> |60  <br/> |
|Maximale Anzahl von Benutzern pro Pool, die für die Gruppenanrufannahme aktiviert sind  <br/> |25.000  <br/> |3,000  <br/> |
|Maximale Rate eingehender Anrufe an alle Benutzer, die für die Gruppenanrufannahme pro Pool und Minute aktiviert sind  <br/> |500  <br/> |60  <br/> |
|Maximale Rate von Anrufen, die von Benutzern mit Gruppenanrufannahme pro Pool und Minute abgerufen wurden  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Berechnen Sie die Metriken für Front-End-Pools mit weniger als acht Front-End-Servern linear. Wenn Ihr Front-End-Pool beispielsweise über einen Front-End-Server verfügt, berechnen Sie die maximale Last als 1/8 der in der Tabelle aufgeführten Werte. 
  
> [!NOTE]
> Sie können die empfohlene Anzahl von Benutzern pro Gruppe und Gruppen erhöhen oder verringern, solange Sie die maximale Anzahl von Benutzern pro Pool nicht überschreiten. Der Standard Edition-Server kann beispielsweise 120 Gruppen mit 25 Benutzern pro Gruppe haben, da die Anzahl der benutzer, die für die Gruppenanrufannahme aktiviert sind, weiterhin innerhalb des maximalen Benutzermodells liegt (d. h. 120 Gruppen mal 25 Benutzer sind 3.000 Benutzer für die Gruppenanrufannahme aktiviert). 
  

