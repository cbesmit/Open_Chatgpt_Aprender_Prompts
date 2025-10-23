{
    // Si tu herramienta exige JSON estricto, elimina todas las líneas de comentarios (// …) antes de subir.
    "schema_version": 1, // versión del esquema de este archivo
    "version": 1, // incrementa +1 en cada actualización
    "updated_at": "YYYY-MM-DD", // fecha ISO de la última edición
    "perfil": { // metadatos del plan de evaluación
        "tema": "{TEMA}", // ej.: MCP, Python, Patrones de diseño, Anatomía, etc.
        "nivel_actual": null, // INICIAL|BASICO|INTERMEDIO|AVANZADO|EXPERTO (null si aún sin diagnóstico)
        "nivel_objetivo": "INTERMEDIO", // meta de nivel para el ciclo
        "ultima_decision": null, // 'promocion'|'mantener'|'replanificar' (última decisión aplicada)
        "tiempo_semana_min": 180, // minutos/semana comprometidos
        "notas": "" // observaciones generales del perfil
    },
    "diagnostico_inicial": { // registro del primer diagnóstico
        "fecha": null, // YYYY-MM-DD
        "score_total": null, // 0..100 (ponderado por secciones)
        "secciones": { // detalle del diagnóstico por sección
            "teoria": {
                "items": 10, // cantidad de ítems teóricos
                "aciertos": null, // correctos
                "score": null, // 0..100 calculado para la sección
                "observaciones": "" // notas breves (errores típicos, omisiones)
            },
            "practica": {
                "tareas": 2, // número de tareas cortas
                "cumplidas": null, // cuántas cumplen criterios mínimos
                "score": null, // 0..100 de la sección
                "observaciones": ""
            },
            "aplicacion": {
                "retos": 1, // mini-reto/caso
                "cumplidos": null, // 0..retos
                "score": null, // 0..100
                "observaciones": ""
            }
        },
        "errores_frecuentes": [ // lista de errores o lagunas detectadas
            // "Confunde A con B",
            // "No justifica el método"
        ],
        "fortalezas": [ // puntos fuertes
            // "Buena lectura de gráficos"
        ],
        "recomendaciones_iniciales": { // qué atacar primero tras el diagnóstico
            "temario": [ // IDs de módulo.tarea sugeridos (si existen)
                // "M1.T1", "M1.T2"
            ],
            "terminos": [ // términos a alta o repaso
                // "concepto_clave_1", "procedimiento_Y"
            ]
        },
        "justificacion": null // explicación breve de la calificación y ruta sugerida
    },
    "examenes": [ // histórico de exámenes periódicos
        {
            // — EJEMPLO DE ESTRUCTURA DE EXAMEN —
            "id": "EX_2025_01", // identificador único del examen
            "fecha": "YYYY-MM-DD",
            "tiempo_min": 30, // minutos utilizados
            "secciones": {
                "teoria": {
                    "items": 12,
                    "aciertos": 9,
                    "score": 75,
                    "errores_frecuentes": [
                        "concepto_A",
                        "definicion_B"
                    ]
                },
                "practica": {
                    "tareas": 2,
                    "cumplidas": 1,
                    "score": 65,
                    "observaciones": "Falta justificar el método"
                },
                "aplicacion": {
                    "retos": 1,
                    "cumplidos": 1,
                    "score": 80
                }
            },
            "ponderacion": {
                "teoria": 0.4,
                "practica": 0.35,
                "aplicacion": 0.25
            }, // si se omite, usar reglas.peso_secciones
            "score_total": 73, // 0..100 calculado con la ponderación
            "observaciones": "Buen desempeño general; reforzar práctica.",
            "recomendaciones": { // acciones hacia otros chats/archivos
                "temario": [
                    {
                        "modulo_id": "M1",
                        "tarea_id": "T2",
                        "motivo": "Cubre error de método"
                    }
                ],
                "terminos": [
                    "termino_X",
                    "procedimiento_Y"
                ]
            },
            "decision_sugerida": "mantener" // 'promocion'|'mantener'|'replanificar'
        }
    ],
    "metricas": { // KPIs agregados para decisiones
        "promedio_ult2": null, // promedio de score_total de los últimos 2 exámenes
        "promedio_ult3": null, // promedio de los últimos 3
        "tendencia_pct": null, // ((score_ultimo - promedio_ult3)/promedio_ult3)*100
        "tasa_completitud": null, // % de tareas cerradas en el periodo (desde temario)
        "retencion_srs": null, // % de retención (desde terminos)
        "streak_estudio_dias": null, // días consecutivos de estudio (opcional)
        "observaciones": "" // notas sobre el comportamiento de KPIs
    },
    "reglas": { // política de decisión
        "peso_secciones": {
            "teoria": 0.4,
            "practica": 0.35,
            "aplicacion": 0.25
        }, // suma 1.0
        "umbral_promocion_total": 75, // score_total mínimo para considerar promoción
        "umbral_mejora_pct": 10, // mejora % vs. anterior/promedio para promover
        "umbral_banda_roja": 60, // sección por debajo de este valor = alerta
        "frecuencia_examen_dias": 7, // sugerido (ajusta según disponibilidad)
        "politica": "Subir si promedio_ult2≥75, tendencia≥+10 y sin secciones<60; si promedio_ult3<60 → plan de refuerzo." // resumen legible
    },
    "historial": [ // bitácora auditada (append-only)
        {
            "fecha": "YYYY-MM-DD",
            "version": 1,
            "tipo": "diagnostico|examen|propuesta_nivel|actualizacion_reglas",
            "resumen": "Se realizó diagnóstico inicial."
        }
    ],
    "referencias": { // enlaces cruzados (opcionales)
        "temario_version_actual": "", // id/fecha de la versión ACTUAL del temario al momento del registro
        "observaciones_cross": "Alinear con evidencias de temario antes de promover nivel."
    }
}