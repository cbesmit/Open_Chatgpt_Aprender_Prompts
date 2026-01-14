{
    // Si tu herramienta exige JSON estricto, elimina todas las líneas de comentarios (// …) antes de subir.
    "schema_version": 1, // versión del esquema de este archivo
    "version": 1, // incrementa +1 en cada actualización
    "updated_at": "YYYY-MM-DD", // fecha ISO de la última edición
    "versiones": [ // lista de snapshots versionados del plan; sólo uno puede estar en ACTUAL
        {
            "fecha": "YYYY-MM-DD", // fecha de creación de esta versión
            "estado": "ACTUAL", // ACTUAL | HISTORICO (una sola ACTUAL)
            "nivel_base": "INICIAL|BASICO|INTERMEDIO|AVANZADO|EXPERTO", // nivel de referencia de la versión
            "horizonte": "Semana 1-2", // rango de semanas/meses que cubre esta versión (sugerido)
            "objetivos_periodo": [ // metas medibles del periodo para orientar módulos
                {
                    "periodo": "Semana 1", // etiqueta del periodo (Semana 1, Sprint 1, etc.)
                    "objetivos": [ // resultados de aprendizaje del periodo (sugerido: 2–5)
                        "Comprender los fundamentos de {TEMA}",
                        "Aplicar {concepto} en un caso simple"
                    ],
                    "kpi": [ // KPIs para medir cumplimiento (nombre+meta)
                        {
                            "nombre": "tasa_completitud",
                            "meta": 0.8,
                            "comentario": "≥80% de tareas cerradas"
                        },
                        {
                            "nombre": "score_total",
                            "meta": 75,
                            "comentario": "Promedio del ciclo en evaluaciones"
                        }
                    ]
                }
            ],
            "modulos": [ // unidades de contenido y práctica
                {
                    "id": "M1", // identificador único del módulo
                    "titulo": "Introducción a {TEMA}",
                    "descripcion": "Panorama general, objetivos, alcance y criterios de cierre.",
                    "dependencias_modulos": [], // IDs de módulos que deben verse antes (si aplica)
                    "prioridad": "alta|media|baja", // priorización del módulo en el periodo
                    "estado": "pendiente|en_progreso|hecho", // estado actual del módulo
                    "contenidos": [ // piezas de conocimiento a cubrir (formato sugerido)
                        {
                            "tipo": "concepto|procedimiento|lectura|video|demo|estandar|reglamento|obra", // categoría del contenido
                            "titulo": "¿Qué es {concepto_clave}?",
                            "descripcion": "Definición y contexto básico para enmarcar el tema.",
                            "recursos": [ // materiales sugeridos para estudiar (formato sugerido)
                                {
                                    "tipo": "articulo|doc|video|curso|dataset|repo|norma",
                                    "titulo": "Recurso de ejemplo",
                                    "url": "https://…",
                                    "obligatorio": true, // si es requerido o opcional
                                    "comentario": "Referencia introductoria, lectura de 10 minutos"
                                }
                            ]
                        }
                    ],
                    "tareas": [ // actividades evaluables alineadas al módulo
                        {
                            "id": "T1", // identificador de la tarea dentro del módulo
                            "tipo": "quiz|problema|caso|laboratorio|implementacion|ensayo|analisis_datos|proyecto|presentacion|debate|lectura_anotada",
                            "titulo": "Actividad inicial de {TEMA}",
                            "descripcion": "Resuelve/realiza la actividad siguiendo las indicaciones del brief.",
                            "dificultad": "baja|media|alta",
                            "horas_estimadas": 60, // tiempo estimado en minutos
                            "criterios_aceptacion": [ // lista de criterios medibles y su peso sugerido
                                {
                                    "criterio": "Resultados correctos en 8/10 ítems",
                                    "peso": 0.4
                                },
                                {
                                    "criterio": "Proceso/metodología justificada",
                                    "peso": 0.3
                                },
                                {
                                    "criterio": "Claridad y formato de entrega",
                                    "peso": 0.3
                                }
                            ],
                            "rubrica_breve": [ // guía de calificación ligera por criterio (formato sugerido)
                                {
                                    "criterio": "Exactitud",
                                    "niveles": {
                                        "1": "Errores graves",
                                        "3": "Adecuado",
                                        "5": "Excelente"
                                    }
                                },
                                {
                                    "criterio": "Método",
                                    "niveles": {
                                        "1": "Confuso",
                                        "3": "Correcto",
                                        "5": "Rigoroso"
                                    }
                                }
                            ],
                            "entregables": [ // lo que debe entregar el alumno/usuario (formato sugerido)
                                {
                                    "tipo": "informe|codigo|slides|dataset|video|prototipo|cuaderno_lab|bitacora",
                                    "ubicacion": "link o ruta prevista (ej: evidencias/semana1/T1.pdf)",
                                    "formato": "pdf|md|ipynb|repo|pptx|csv",
                                    "obligatorio": true
                                }
                            ],
                            "evidencias": [ // evidencias que validan criterios de aceptación (formato sugerido)
                                {
                                    "id": "E1",
                                    "descripcion": "Captura de resultados / PR / enlace a demo",
                                    "criterios_validacion": [
                                        "Demuestra cumplimiento de C1 y C2",
                                        "Incluye fuente/datos o justificación"
                                    ],
                                    "ubicacion": "evidencias/semana1/pr1.pdf",
                                    "estado": "pendiente|en_revision|validada",
                                    "fecha_subida": null // YYYY-MM-DD cuando se adjunte
                                }
                            ],
                            "observaciones": "Notas breves del revisor/usuario",
                            "relacion_terminos": [ // vínculo con términos SRS (para altas o refuerzos)
                                {
                                    "id": "K1",
                                    "nombre": "{termino_clave}",
                                    "accion": "reforzar|alta_nueva"
                                }
                            ]
                        }
                    ],
                    "criterios_cierre_modulo": [ // condiciones mínimas para marcar el módulo como "hecho"
                        "Al menos 1 evidencia validada",
                        "Mini-test del módulo ≥ 70%"
                    ],
                    "evidencias": [ // evidencias globales del módulo (portafolio, PR final, demo) (formato sugerido)
                        {
                            "id": "EM1",
                            "tipo": "portafolio|PR|presentacion|reporte|prototipo|resultado_medicion",
                            "descripcion": "Evidencia integradora del módulo",
                            "criterios_validacion": [
                                "Cubre los objetivos del módulo",
                                "Revisado por docente/IA"
                            ],
                            "ubicacion": "evidencias/modulo1/portafolio.zip",
                            "estado": "pendiente|en_revision|validada",
                            "fecha_subida": null
                        }
                    ],
                    "metricas_modulo": { // métricas locales del módulo
                        "tasa_completitud": null, // 0..1 porcentaje de tareas completas
                        "score_estimado": null, // 0..100 si existe calificación del módulo
                        "retrasos": 0 // semanas de retraso acumulado
                    }
                }
            ],
            "resumen_actual": { // atajo semanal: qué hacer ahora mismo
                "periodo": "Semana 1",
                "objetivos_clave": [
                    "Comprender fundamentos",
                    "Aplicar concepto X"
                ],
                "tareas_clave": [
                    {
                        "modulo_id": "M1",
                        "tarea_id": "T1",
                        "criterios": [
                            "C1 resultados",
                            "C2 método"
                        ],
                        "evidencias_esperadas": [
                            "EM1 portafolio inicial"
                        ]
                    }
                ]
            },
            "observaciones": [ // notas de coordinación, decisiones y riesgos
                "Sin recursos críticos pendientes",
                "Revisar lagunas SRS en {tema} antes del siguiente módulo"
            ]
        }
    ]
}