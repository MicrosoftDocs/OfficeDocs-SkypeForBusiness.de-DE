---
title: Planen der Gruppenanrufannahme in Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Planung für Gruppe aufrufen Pickup-in Skype für Business Server Enterprise-VoIP, können die Benutzer Annahme von Anrufen, die ursprünglich für andere Benutzer vorgesehen.
ms.openlocfilehash: 6a2fde93d6fcbfa4e2b382f3512d65a8d986a8ba
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-group-call-pickup-in-skype-for-business-2015"></a>Planen der Gruppenanrufannahme in Skype for Business 2015
 
Planung für Gruppe aufrufen Pickup-in Skype für Business Server Enterprise-VoIP, können die Benutzer Annahme von Anrufen, die ursprünglich für andere Benutzer vorgesehen.
  
Gruppe aufrufen Pickup-ermöglicht Benutzern, eingehende Anrufe an ihre Kollegen aus ihrer eigenen Telefone zu beantworten. Dies erhöht die Verfügbarkeit der Zeile eines Benutzers durch andere Benutzer beantworten ein eingehenden Anrufs durch Wählen einer Rufnummer des Anrufs pickup Gruppe aktivieren. Bei der Gruppe anrufen Pickup-bereitgestellt wird, kann die Anzahl der eingehenden Anrufe, die an die Voicemail weitergeleitet werden deutlich reduziert werden die eignet sich besonders für Anrufe von Kunden, die sich außerhalb Ihrer Organisation befinden.
  
Die Gruppe aufrufen Pickup--Funktion ist insbesondere für Geschäftseinheiten in Umgebungen mit Office open vorgesehen. Eingehende Anrufe stören nicht, da sie nur am vorgesehenen Zieltelefon klingeln. Andere Benutzer, die das Klingeln hören, können den Anruf dennoch annehmen, indem sie einfach die Gruppennummer wählen. 
  
In Umgebungen, in denen sich Benutzer nicht in einer offenen Büroanordnung oder – trotz gemeinsamer Verantwortungsbereiche – an verschiedenen geografischen Standorten befinden, ist die Teamanruffunktion die am besten geeignete Lösung. Der Hauptunterschied zwischen Gruppe aufrufen Pickup- und teamanrufe ist, dass mit Gruppe Pickup-aufrufen, ein eingehender Anruf nur an das vorgesehene Ziel klingelt, aber jeder kann dennoch zum Annehmen des Anrufs durch Wählen einer Rufnummer für die Gruppe auswählen. Bei einem Teamanruf klingeln die Telefone aller Gruppenmitglieder und jeder Benutzer im Team kann den Anruf annehmen. Ein weiterer Unterschied zwischen Gruppe aufrufen Pickup- und teamanrufe ist, dass die Gruppe aufrufen Pickup-vom Administrator über Skype für Business Server verwaltet wird. Mit teamanruf verwalten die Endbenutzer das Feature mithilfe der Skype für Business-Client. Mit Gruppe Pickup-aufrufen kann daher dieser Aspekt anrufverwaltung zentralisiert.
  
Gruppe aufrufen Pickup-baut auf die Anwendung zum Parken. Bei der Bereitstellung von Gruppe aufrufen Pickup-konfigurieren Sie die orbittabelle für das Parken von Anrufen mit separaten Bereichen von Durchwahlnummern, die als Rufnummern pickup Gruppe festgelegt sind. Wie bei Orbitnummern zum Parken von Anrufen muss es sich auch bei Nummern für die Anrufannahmegruppe um virtuelle Durchwahlen handeln, denen kein Benutzer oder Telefon zugewiesen ist. Jeder Front-End-Pool, in der Gruppe anrufen Pickup-bereitstellen, kann ein oder mehrere Bereiche des pickup Gruppe Rufnummern haben. Die Gruppenbereiche müssen für die Skype für Business Server-Bereitstellung global eindeutig sein. 
  
> [!NOTE]
> Bereiche, die als Gruppe aufrufen Pickup-festgelegt sind, Zahlen in der orbittabelle für das Parken von Anrufen nicht verwaltete oder mithilfe der Skype Business Server-Systemsteuerung angezeigt werden. Die einzige Möglichkeit, alle Nummernbereiche in der orbittabelle für das Parken von Anrufen finden Sie unter ist Skype für Business Server-Verwaltungsshell verwenden. In ähnlicher Weise die einzige Möglichkeit zum Hinzufügen, ändern oder entfernen Gruppe aufrufen Pickup-Zahlen ist Skype für Business Server-Verwaltungsshell verwenden. 
  
Nach dem Konfigurieren der Nummern für die Anrufannahmegruppe weisen Sie Benutzer einer Anrufannahmegruppe zu. Die Anrufe jedes Benutzers, der einer Anrufannahmegruppe zugewiesen ist, können von anderen Personen angenommen werden. Wenn ein Anruf an einen Benutzer eingeht, der einer Anrufannahmegruppe zugewiesen ist, kann ein beliebiger anderer Benutzer diesen Anruf annehmen, indem er manuell die Nummer für die Anrufannahmegruppe wählt. Der Benutzer, der den Anruf annimmt, muss kein Mitglied der Gruppe sein. Wenn ein Anruf von einem anderen Benutzer angenommen wird, wird eine Benachrichtigung an den Benutzer gesendet, dessen Nummer ursprünglich gewählt wurde.
  
> [!NOTE]
> Ein Benutzer kann nur in einer Anrufannahmegruppe Mitglied sein. 
  
> [!NOTE]
> Obwohl jeder Benutzer in der Skype für Business Server-Bereitstellung einen Anruf an ein pickup Gruppenmitglied Anruf entgegennehmen kann, muss die Person, die den Anruf die richtigen pickup-Gruppe zu wählende Nummer kennen. 
  
Wenn ein Benutzer zum Annehmen eines Anrufs die Nummer für die Anrufannahmegruppe wählt und mehrere Telefone in der Gruppe klingeln, nimmt der Benutzer den Anruf an, der bereits am längsten klingelt.
  
Gleichzeitige Klingeln Einstellungen funktionieren für Benutzer, die Gruppe Pickup aufgerufen haben. D. h., ein Anruf versucht, ein Benutzer, der Gruppe anrufen Pickup-klingelt für alle konfigurierten Ziele, und ein anderer Benutzer den Anruf entgegennehmen kann. Eine Ausnahme zu dieser Regel tritt auf, wenn der Benutzer gleichzeitig eingehende Anrufe so konfiguriert, dass sie an alle Teammitglieder eingehen.
  
Gruppe aufrufen Pickup-kann nicht verwendet werden, die folgenden Arten von Anrufen zu beantworten:
  
- Anrufe an eine Privatleitung
    
- Anrufe von Kontakten, denen die private Beziehung „Freunde und Familie“ zugewiesen wurde
    
    > [!TIP]
    > Ein Benutzer, der Mitglied einer pickup anrufgruppe ist kann verhindern, dass bestimmte Anrufe über Gruppe aufrufen Pickup-durch markieren den Kontakt als einen persönlichen Kontakt in der Skype für Business Client abgerufen werden. Zum Kennzeichnen eines Kontakts als persönlichen Kontakt legen Sie die private Beziehung für den Kontakt auf „Freunde und Familie“ fest. Legen Sie alle eingehender Anruf von Kontakten mit der privaten Beziehung Freunde und Familie kann nicht mit der Gruppe anrufen Pickup-abgerufen werden. 
  
- Videoteil von Audio-/Videoanrufen 
    
    > [!NOTE]
    > Wenn ein Benutzer einen Audio-/Videoanruf annimmt, empfängt er nur den Audioteil. Der Anruf kann entweder vom Anrufer oder von der Person, die den Anruf annimmt, hochgestuft und damit der Videoteil hinzugefügt werden. 
  
- Gleichzeitig eingehende Anrufe, die an Teamanrufmitglieder weitergeleitet werden
    
- An einen Stellvertreter weitergeleitete Anrufe
    
- An eine Antwortgruppe weitergeleitete Anrufe
    
Die folgenden Arten von Benutzern können nicht in der Gruppe anrufen Pickup-teilnehmen. D. h., sie sollten nicht in einer Gruppe anrufen Pickup-Gruppe eingeschlossen werden, und sie können keine Anrufe für Benutzer, die Gruppe aufrufen Pickup-aktiviert haben aufzunehmen.
  
- Benutzer, die online in einer Hybridbereitstellung gehostet sind
    
- Benutzer, die nicht auf entweder einen Skype für Business Server 2015 Pool oder ein Lync Server 2013-Pool mit kumulativen Updates für Lync Server 2013 befinden: in einer lokalen Bereitstellung für Februar 2013
    
Wenn ein Anruf an ein Mitglied einer Anrufannahmegruppe nicht angenommen wird, wird der Anruf gemäß den Angaben in den Clienteinstellungen weitergeleitet. Das bedeutet, dass der Anruf an Voicemail oder wie in den Clienteinstellungen angegeben an ein anderes Zieltelefon weitergeleitet wird.
  
## <a name="deployment-and-requirements"></a>Bereitstellung und Anforderungen

Gruppe aufrufen Pickup-wird automatisch bereitgestellt, bei der Bereitstellung von Enterprise-VoIP und die Anwendung zum Parken. Gruppe aufrufen Pickup-aktiviert, indem der orbittabelle für das Parken von Anrufen mit separaten Bereichen von Zahlen festgelegte als Anruf pickup Gruppe Zahlen und klicken Sie dann durch Zuweisen von Benutzern zu Gruppen pickup aufrufen und aktivieren die Benutzer für die Gruppe aufrufen Pickup-konfigurieren.
  
## <a name="clients-supported-for-group-call-pickup"></a>Für die Gruppe aufrufen Pickup-unterstützte Clients

Eine der folgenden Clients können Annahme von Anrufen an Mitglieder der Gruppe anrufen Pickup-verwendet werden:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Benutzer können alle diese Clients Annahme von Anrufen an Mitglieder der Gruppe anrufen Pickup-verwenden, aber der Benutzer müssen auf einen Skype für Business Server oder Pool mit einem Lync Server 2013 mit kumulativen Updates für Lync Server 2013 verwaltet werden: für Februar 2013. 
  
Die folgenden Clients und Geräten sind für Anrufe an die Mitglieder der Gruppe anrufen Pickup-abnehmen nicht unterstützt:
  
- Lync Mobile
    
- Lync-App für Windows 8 und Windows RT
    
- Lync für iPad
    
- Analoge Telefone
    
- Telefone mit PSTN-Nummern (Telefonfestnetznummern)
    
## <a name="capacity-planning"></a>Kapazitätsplanung

Die folgende Tabelle beschreibt das Gruppe aufrufen Pickup-Benutzermodell, das Sie als Grundlage für Anforderungen an die kapazitätsplanung verwenden können.
  
> [!IMPORTANT]
> Gruppe aufrufen Pickup-basiert auf die Anwendung zum Parken. Beachten Sie, dass bei der Disaster Recovery kapazitätsplanung jeder Pool eines gekoppelten Pools die Arbeitslast für das Parken von Anrufen-Dienste, einschließlich Gruppe aufrufen Pickup-, in beiden Pools kann soll beibehalten. 
  
**Gruppe Anruf Pickup-Benutzermodell**

|**Metrik**|**Pro Front-End-Pool <br/> (mit 8 Front-End-Servern)**|**Pro Standard Edition-server**|
|:-----|:-----|:-----|
|Empfohlene Benutzeranzahl pro Gruppe  <br/> |50  <br/> |50  <br/> |
|Empfohlene Gruppenanzahl  <br/> |500  <br/> |60  <br/> |
|Maximale Anzahl der für die Gruppenanrufannahme aktivierten Benutzer pro Pool  <br/> |25.000  <br/> |3.000  <br/> |
|Maximale Rate an eingehenden Anrufen pro Pool und Minute an alle Benutzer, die für die Gruppenanrufannahme aktiviert sind  <br/> |500  <br/> |60  <br/> |
|Maximale Rate an von Benutzern mit Gruppenanrufannahme wieder aufgenommenen Anrufen pro Pool und Minute  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Berechnen Sie die Metriken für Front-End-Pools, die weniger als acht Front-End-Server verfügen, linear. Wenn der Front-End-Pool einen Front-End-Server verfügt, berechnen Sie die maximale Last beispielsweise als 1/8, der in der Tabelle aufgeführten Werte. 
  
> [!NOTE]
> Sie können die empfohlene Anzahl von Benutzern pro Gruppe erhöhen oder reduzieren, solange die maximale Anzahl von Benutzern pro Pool nicht überschritten wird. Beispielsweise kann Standard Edition-Servers 120 Gruppen mit 25 Benutzer pro Gruppe aufweisen, da die Anzahl der Benutzer für die Gruppe aufrufen Pickup-aktiviert ist weiterhin innerhalb der Benutzer Modell maximale (d. h., 120 Gruppen Mal 25 Benutzer 3.000 Benutzer für die Gruppe aufrufen Pickup-aktiviert ist). 
  

