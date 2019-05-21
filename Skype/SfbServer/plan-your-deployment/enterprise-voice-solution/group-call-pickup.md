---
title: Planen der Abholung von Gruppen anrufen in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Planung für die Gruppenanruf Abholung in Skype for Business Server Enterprise-VoIP, mit der Benutzer Anrufe annehmen können, die ursprünglich für andere vorgesehen sind.
ms.openlocfilehash: c729e2d672d104337820c44fa41c113dded3110f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276838"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Planen der Abholung von Gruppen anrufen in Skype for Business
 
Planung für die Gruppenanruf Abholung in Skype for Business Server Enterprise-VoIP, mit der Benutzer Anrufe annehmen können, die ursprünglich für andere vorgesehen sind.
  
Mit der Gruppenanruf Abholung können Benutzer eingehende Anrufe an Ihre Kollegen über ihre eigenen Telefone annehmen. Dadurch wird die Verfügbarkeit der Benutzer Zeile erhöht, da andere Benutzer die Möglichkeit haben, einen eingehenden Anruf zu beantworten, indem Sie eine Anruf-Abhol Gruppennummer wählen. Wenn die Gruppenanruf Abholung bereitgestellt wird, kann die Anzahl der eingehenden Anrufe, die an die Voicemail weitergeleitet werden, erheblich reduziert werden, was besonders für Anrufe von Kunden nützlich ist, die sich außerhalb Ihrer Organisation befinden.
  
Das Feature für die Gruppenanruf Abholung ist insbesondere für Unternehmenseinheiten in offenen Office-Umgebungen konzipiert. Eingehende Anrufe stören nicht, da sie nur am vorgesehenen Zieltelefon klingeln. Andere Benutzer, die das Klingeln hören, können den Anruf dennoch annehmen, indem sie einfach die Gruppennummer wählen. 
  
In Umgebungen, in denen sich Benutzer nicht in einer offenen Büroanordnung oder – trotz gemeinsamer Verantwortungsbereiche – an verschiedenen geografischen Standorten befinden, ist die Teamanruffunktion die am besten geeignete Lösung. Der Hauptunterschied zwischen Gruppenanruf Abholung und Teamanruf besteht darin, dass ein eingehender Anruf nur an dem vorgesehenen Ziel klingelt, aber jeder kann ihn trotzdem durch Wählen einer Gruppennummer beantworten. Bei einem Teamanruf klingeln die Telefone aller Gruppenmitglieder und jeder Benutzer im Team kann den Anruf annehmen. Ein weiterer Unterschied zwischen Gruppenanruf Abholung und Teamanruf besteht darin, dass die Abholung von Gruppen anrufen von einem Administrator über Skype for Business Server verwaltet wird. Mit Team Anruf verwalten Endbenutzer das Feature mithilfe des Skype for Business-Clients. Mit der Gruppenanruf-Abholung kann dieser Aspekt der Anrufverwaltung also zentralisiert werden.
  
Die Abholung von Gruppen anrufen basiert auf der Anwendung für den Anruf Park. Wenn Sie die Gruppenanruf Abholung bereitstellen, konfigurieren Sie die Orbit-Tabelle des Anruf Parks mit getrennten Bereichen von Durchwahlnummern, die als Gruppennummern für die Anruf Abholung festgelegt sind. Wie bei Orbitnummern zum Parken von Anrufen muss es sich auch bei Nummern für die Anrufannahmegruppe um virtuelle Durchwahlen handeln, denen kein Benutzer oder Telefon zugewiesen ist. Jeder Front-End-Pool, in dem Sie die Gruppenanruf Abholung bereitstellen, kann über einen oder mehrere Bereiche der Gruppennummern für die Anruf Abholung verfügen. Die Gruppennummern Bereiche müssen für die Bereitstellung von Skype for Business Server global eindeutig sein. 
  
> [!NOTE]
> Nummernkreise, die als Gruppenanruf-Abhol Nummern in der Orbit-Tabelle des Anruf Parks bezeichnet werden, können mithilfe der Skype for Business Server-Systemsteuerung nicht verwaltet oder angezeigt werden. Die einzige Möglichkeit, alle Nummernbereiche in der Orbit-Tabelle des Anruf Parks anzuzeigen, besteht darin, die Skype for Business Server-Verwaltungsshell zu verwenden. Ebenso besteht die einzige Möglichkeit zum Hinzufügen, ändern oder Entfernen von Gruppenanruf-Pickup-Nummern darin, die Skype for Business Server-Verwaltungsshell zu verwenden. 
  
Nach dem Konfigurieren der Nummern für die Anrufannahmegruppe weisen Sie Benutzer einer Anrufannahmegruppe zu. Die Anrufe jedes Benutzers, der einer Anrufannahmegruppe zugewiesen ist, können von anderen Personen angenommen werden. Wenn ein Anruf an einen Benutzer eingeht, der einer Anrufannahmegruppe zugewiesen ist, kann ein beliebiger anderer Benutzer diesen Anruf annehmen, indem er manuell die Nummer für die Anrufannahmegruppe wählt. Der Benutzer, der den Anruf annimmt, muss kein Mitglied der Gruppe sein. Wenn ein Anruf von einem anderen Benutzer angenommen wird, wird eine Benachrichtigung an den Benutzer gesendet, dessen Nummer ursprünglich gewählt wurde.
  
> [!NOTE]
> Ein Benutzer kann nur in einer Anrufannahmegruppe Mitglied sein. 
  
> [!NOTE]
> Obwohl jeder Benutzer in der Skype for Business Server-Bereitstellung einen Anruf an ein Mitglied der Anruf Abholungs Gruppe annehmen kann, muss die Person, die den Anruf annimmt, die richtige Anruf-Abhol Gruppennummer kennen, um zu wählen. 
  
Wenn ein Benutzer zum Annehmen eines Anrufs die Nummer für die Anrufannahmegruppe wählt und mehrere Telefone in der Gruppe klingeln, nimmt der Benutzer den Anruf an, der bereits am längsten klingelt.
  
Einstellungen für gleichzeitig eingehende Anrufe funktionieren für Benutzer mit GroupCallPickup. Das bedeutet, dass ein Anruf an einen Benutzer, der eine Gruppenanruf-Abholung hat, für alle konfigurierten Ziele klingelt und ein anderer Benutzer den Anruf annehmen kann. Eine Ausnahme zu dieser Regel tritt auf, wenn der Benutzer gleichzeitig eingehende Anrufe so konfiguriert, dass sie an alle Teammitglieder eingehen.
  
Die Gruppenanruf Abholung kann nicht zur Beantwortung der folgenden Anrufarten verwendet werden:
  
- Anrufe an eine Privatleitung
    
- Anrufe von Kontakten, denen die private Beziehung „Freunde und Familie“ zugewiesen wurde
    
    > [!TIP]
    > Ein Benutzer, der Mitglied einer Anruf Abhol Gruppe ist, kann verhindern, dass bestimmte Anrufe über die Gruppenanruf Abholung abgerufen werden, indem der Kontakt als persönlicher Kontakt im Skype for Business-Client markiert wird. Zum Kennzeichnen eines Kontakts als persönlichen Kontakt legen Sie die private Beziehung für den Kontakt auf „Freunde und Familie“ fest. Alle eingehenden Anrufe von Kontakten mit der privaten Beziehung, die auf Freunde und Familie eingestellt sind, können mit der Gruppenanruf-Abholung nicht abgerufen werden. 
  
- Videoteil von Audio-/Videoanrufen 
    
    > [!NOTE]
    > Wenn ein Benutzer einen Audio-/Videoanruf annimmt, empfängt er nur den Audioteil. Der Anruf kann entweder vom Anrufer oder von der Person, die den Anruf annimmt, hochgestuft und damit der Videoteil hinzugefügt werden. 
  
- Gleichzeitig eingehende Anrufe, die an Teamanrufmitglieder weitergeleitet werden
    
- An einen Stellvertreter weitergeleitete Anrufe
    
- An eine Antwortgruppe weitergeleitete Anrufe
    
Die folgenden Benutzertypen können nicht an der Gruppenanruf Abholung teilnehmen. Das heißt, Sie sollten nicht in eine Gruppenanruf-Abhol Gruppe aufgenommen werden, und Sie können keine Anrufe für Benutzer aufnehmen, die die Gruppenanruf Abholung aktiviert haben.
  
- Benutzer, die online in einer Hybridbereitstellung gehostet sind
    
- Benutzer, die nicht in einem Skype for Business Server 2015-Pool oder einem lync Server 2013-Pool mit kumulativen Updates für lync Server 2013: Februar 2013 in einer lokalen Bereitstellung verwaltet werden
    
Wenn ein Anruf an ein Mitglied einer Anrufannahmegruppe nicht angenommen wird, wird der Anruf gemäß den Angaben in den Clienteinstellungen weitergeleitet. Das bedeutet, dass der Anruf an Voicemail oder wie in den Clienteinstellungen angegeben an ein anderes Zieltelefon weitergeleitet wird.
  
## <a name="deployment-and-requirements"></a>Bereitstellung und Anforderungen

Die Gruppenanruf Abholung wird automatisch bereitgestellt, wenn Sie Enterprise-VoIP und die Anwendung für den Anruf Park bereitstellen. Sie aktivieren die Abholung von Gruppen anrufen, indem Sie die Umlaufbahn Tabelle des Anruf Parks mit getrennten Nummernbereichen konfigurieren, die als Gruppennummern für die Anruf Abholung bestimmt sind, und dann durch Zuweisen von Benutzern zum Anrufen von Abhol Gruppen und zum Aktivieren der Gruppenanruf Abholung.
  
## <a name="clients-supported-for-group-call-pickup"></a>Für die Gruppenanruf Abholung unterstützte Clients

Alle folgenden Clients können verwendet werden, um Anrufe an Gruppenanruf-Pickup-Mitglieder zu beantworten:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Benutzer können mit jedem dieser Clients Anrufe an Gruppenanruf-Pickup-Mitglieder annehmen, aber die Benutzer müssen sich in einem Skype for Business-Serverpool oder einem lync Server 2013-Pool mit kumulativen Updates für lync Server 2013: Februar 2013 befinden. 
  
Die folgenden Clients und Geräte werden für die Abholung von Anrufen an Gruppenanruf-Pickup-Mitglieder nicht unterstützt:
  
- Lync Mobile
    
- Lync-App für Windows 8 und Windows RT
    
- Lync für iPad
    
- Analoge Telefone
    
- Telefone mit PSTN-Nummern (Telefonfestnetznummern)
    
## <a name="capacity-planning"></a>Kapazitätsplanung

In der folgenden Tabelle wird das Benutzermodell für die Gruppenanruf Abholung beschrieben, das Sie als Grundlage für die Kapazitäts Planungsanforderungen verwenden können.
  
> [!IMPORTANT]
> Die Abholung von Gruppen anrufen basiert auf der Anwendung "Parken". Beachten Sie, dass für die Planung von Disaster Recovery-Kapazität jeder Pool eines gekoppelten Pools in der Lage sein sollte, die Arbeitsauslastungen für die Anruf Park Dienste, einschließlich der Gruppenanruf Abholung, in beiden Pools zu verarbeiten. 
  
**Gruppenanruf-Pickup-Benutzermodell**

|**Metrik**|**Pro Front-End <br/> -Pool (mit 8 Front-End-Servern)**|**Pro Standard Edition-Server**|
|:-----|:-----|:-----|
|Empfohlene Benutzeranzahl pro Gruppe  <br/> |50  <br/> |50  <br/> |
|Empfohlene Gruppenanzahl  <br/> |500  <br/> |60  <br/> |
|Maximale Anzahl der für die Gruppenanrufannahme aktivierten Benutzer pro Pool  <br/> |25.000  <br/> |3.000  <br/> |
|Maximale Rate an eingehenden Anrufen pro Pool und Minute an alle Benutzer, die für die Gruppenanrufannahme aktiviert sind  <br/> |500  <br/> |60  <br/> |
|Maximale Rate an von Benutzern mit Gruppenanrufannahme wieder aufgenommenen Anrufen pro Pool und Minute  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Für Front-End-Pools mit weniger als acht Front-End-Servern berechnen Sie die Metriken linear. Wenn der Front-End-Pool beispielsweise über einen Front-End-Server verfügt, berechnen Sie die maximale Auslastung als 1/8 der in der Tabelle angegebenen Werte. 
  
> [!NOTE]
> Sie können die empfohlene Anzahl von Benutzern pro Gruppe erhöhen oder reduzieren, solange die maximale Anzahl von Benutzern pro Pool nicht überschritten wird. Beispielsweise kann Ihr Standard Edition-Server 120-Gruppen mit 25 Benutzern pro Gruppe haben, da die Anzahl der Benutzer, die für die Gruppenanruf-Abholung aktiviert sind, sich noch innerhalb des maximal zulässigen Benutzermodells befindet (das heißt, 120 Gruppen mal 25 Benutzer sind 3.000 Benutzer, die für Gruppenanruf-Pickups aktiviert sind). 
  

