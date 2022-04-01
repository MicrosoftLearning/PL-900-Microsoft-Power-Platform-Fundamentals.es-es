---
title: Instrucciones hospedadas en línea
permalink: index.html
layout: home
ms.openlocfilehash: f4e2e1489e1997cfd064aa74eb5345e302bb2424
ms.sourcegitcommit: ef58c858463b890e923ef808b1d43405423943fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2022
ms.locfileid: "137899014"
---
# <a name="content-directory"></a>Directorio de contenido

A continuación se enumeran hipervínculos a cada uno de los ejercicios de laboratorio y demostraciones.

## <a name="labs"></a>Laboratorios

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %}
| Módulo | Laboratorio |
| --- | --- | 
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}

## <a name="demos"></a>Demostraciones

{% assign demos = site.pages | where_exp:"page", "page.url contains '/Instructions/Demos'" %}
| Módulo | Demostración |
| --- | --- | 
{% for activity in demos  %}| {{ activity.demo.module }} | [{{ activity.demo.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
