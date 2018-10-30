---
title: Übersicht über die Gruppenanrufannahme
TOCTitle: Übersicht über die Gruppenanrufannahme
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945623(v=OCS.15)
ms:contentKeyID: 52056341
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über die Gruppenanrufannahme

 

_**Letztes Änderungsdatum des Themas:** 2013-02-12_

Mit der Gruppenanrufannahme, einem neuen Feature in den kumulativen Updates für Lync Server 2013: Februar 2013, können Benutzer eingehende Anrufe an Kollegen an ihren eigenen Telefonen annehmen. Dieses neue Feature erhöht die Verfügbarkeit der Telefonleitung eines Benutzers, da andere Benutzer eingehende Anrufe annehmen können, indem sie eine Nummer für die Anrufannahmegruppe wählen. Bei der Bereitstellung der Gruppenanrufannahme kann die Anzahl der eingehenden Anrufe, die an Voicemail weitergeleitet werden, erheblich reduziert werden. Dies ist insbesondere für Kunden nützlich, die von außerhalb Ihrer Organisation anrufen.

Das Gruppenanrufannahme-Feature wurde insbesondere für Geschäftseinheiten in offenen Büroumgebungen entworfen. Eingehende Anrufe stören nicht, da sie nur am vorgesehenen Zieltelefon klingeln. Andere Benutzer, die das Klingeln hören, können den Anruf dennoch annehmen, indem sie einfach die Gruppennummer wählen.

In Umgebungen, in denen sich Benutzer nicht in einer offenen Büroanordnung befinden, oder in der sich Benutzer mit gemeinsamen Verantwortungsbereichen an verschiedenen geografischen Standorten befinden, stellen die Teamanruffunktion die am besten geeignete Lösung dar. Der Hauptunterschied zwischen der Gruppenanrufannahme und dem Teamanruf besteht darin, dass bei der Gruppenanrufannahme ein eingehender Anruf nur am vorgesehenen Zieltelefon klingelt, aber dennoch von einer beliebigen Person angenommen werden kann, wenn diese eine Gruppennummer wählt. Bei einem Teamanruf klingeln die Telefone aller Gruppenmitglieder, und jeder Benutzer im Team kann den Anruf annehmen. Ein weiterer Unterschied zwischen der Gruppenanrufannahme und Teamanrufen besteht darin, dass die Gruppenanrufannahme über Lync Server von einem Administrator verwaltet wird. Das Teamanruf-Feature wird mithilfe des Lync-Clients von Endbenutzern verwaltet. Daher kann bei der Gruppenanrufannahme dieser Aspekt der Anrufverwaltung zentralisiert werden.

Die Gruppenanrufannahme basiert auf der Anwendung zum Parken von Anrufen. Wenn Sie die Gruppenanrufannahme bereitstellen, konfigurieren Sie Orbittabelle für das Parken von Anrufen mit separaten Durchwahlnummernbereichen, die als Nummern für die Anrufannahmegruppe festgelegt sind. Wie bei Orbitnummern zum Parken von Anrufen muss es sich auch bei Nummern für die Anrufannahmegruppe um virtuelle Durchwahlen handeln, denen kein Benutzer oder Telefon zugewiesen ist. In jedem Front-End-Pool, in dem Sie die Gruppenanrufannahme bereitstellen, kann mindestens ein Nummernbereich für die Anrufannahmegruppe vorhanden sein. Die Gruppennummernbereiche müssen in der Lync Server-Bereitstellung global eindeutig sein.


> [!NOTE]
> Nummernbereiche, die in der Orbittabelle für das Parken von Anrufen als Nummern für die Gruppenanrufannahme festgelegt sind, können nicht mithilfe der Lync Server-Systemsteuerung verwaltet oder angezeigt werden. Die einzige Möglichkeit zum Anzeigen aller Nummernbereiche in der Orbittabelle für das Parken von Anrufen ist die Verwendung der Lync Server-Verwaltungsshell. Entsprechen können Nummern für die Gruppenanrufannahme nur mithilfe der Lync Server-Verwaltungsshell hinzugefügt, geändert oder entfernt werden.



Nach dem Konfigurieren der Nummern für die Anrufannahmegruppe weisen Sie Benutzer einer Anrufannahmegruppe zu. Die Anrufe jedes Benutzers, der einer Anrufannahmegruppe zugewiesen ist, können von anderen Personen angenommen werden. Wenn ein Anruf an einen Benutzer eingeht, der einer Anrufannahmegruppe zugewiesen ist, kann ein beliebiger anderer Benutzer diesen Anruf annehmen, indem er manuell die Nummer für die Anrufannahmegruppe wählt. Der Benutzer, der den Anruf annimmt, muss kein Mitglied der Gruppe sein. Wenn ein Anruf von einem anderen Benutzer angenommen wird, wird eine Benachrichtigung an den Benutzer gesendet, dessen Nummer ursprünglich gewählt wurde.


> [!NOTE]
> Ein Benutzer kann nur in einer Anrufannahmegruppe Mitglied sein.




> [!NOTE]
> Ein Anruf an ein Mitglied einer Anrufannahmegruppe kann zwar von jedem Benutzer in der Lync Server-Bereitstellung angenommen werden, der betreffende Benutzer muss jedoch die richtige Nummer für die Anrufannahmegruppe wählen.



Wenn ein Benutzer zum Annehmen eines Anrufs die Nummer für die Anrufannahmegruppe wählt, und mehrere Telefone in der Gruppe klingeln, nimmer der Benutzer den Anruf an, der bereits am längsten klingelt.

Einstellungen für gleichzeitig eingehende Anrufe funktionieren für Benutzer mit Gruppenanrufannahme. Das bedeutet, dass ein Anruf an einen Benutzer mit Gruppenanrufannahme auf allen konfigurierten Zieltelefonen klingelt, und ein anderer Benutzer den Anruf annehmen kann. Eine Ausnahme zu dieser Regel erfolgt, wenn der Benutzer gleichzeitige eingehende Anrufe so konfiguriert, dass sie an alle Teammitglieder eingehen.

Die Gruppenanrufannahme kann nicht zum Annehmen der folgenden Anruftypen verwendet werden:

  - Anrufe an eine Privatleitung

  - Anrufe von Kontakten, denen die private Beziehung "Freunde und Familie" zugewiesen wurde
    

    > [!TIP]
    > Ein Benutzer, der Mitglied einer Anrufannahmegruppe ist, kann die Annahme bestimmter Anrufe über die Gruppenanrufannahme verhindern, indem er den Kontakt im Lync-Client als persönlichen Kontakt kennzeichnet. Zum Kennzeichnen eines Kontakts als persönlichen Kontakt legen Sie die private Beziehung für den Kontakt auf "Freunde und Familie" fest. Eingehende Anrufe von Kontakten mit der privaten Beziehung "Freunde und Familie" können nicht über die Gruppenanrufannahme angenommen werden.



  - Videoteil von Audio-/Videoanrufen
    

    > [!NOTE]
    > Wenn ein Benutzer einen Audio-/Videoanruf annimmt, empfängt der Benutzer nur den Audioteil. Der Anruf kann entweder vom Anrufer oder von der Person, die den Anruf annimmt, hochgestuft und damit der Videoteil hinzugefügt werden.



  - Gleichzeitig eingehende Anrufe, die an Teamanrufmitglieder weitergeleitet werden

  - An einen Stellvertreter weitergeleitete Anrufe

  - An eine Antwortgruppe weitergeleitete Anrufe

Folgende Benutzertypen können nicht an der Gruppenanrufannahme teilnehmen. Das bedeutet, dass sie keiner Gruppe für die Gruppenanrufannahme angehören sollten, und sie können keine Anrufer an Benutzer annehmen, für die die Gruppenanrufannahme aktiviert ist.

  - Benutzer, die online in einer Hybridbereitstellung gehostet sind

  - Benutzer, die nicht in einem Lync Server 2013-Pool mit den kumulativen Updates für Lync Server 2013: Februar 2013 in einer lokalen Bereitstellung gehostet sind

Wenn ein Anruf an ein Mitglied einer Anrufannahmegruppe nicht angenommen wird, wird der Anruf gemäß den Angaben in den Clienteinstellungen weitergeleitet. Das bedeutet, dass der Anruf an Voicemail oder wie in den Clienteinstellungen angegeben an ein anderes Zieltelefon weitergeleitet wird.

