## SE USO PARA LA SESION DE AUTOMATIZACION

## Paso 0: Vinculación
gcloud init

## Paso 1: Creación del repositorio
gcloud artifacts repositories create repo-mlops12-streamlit-regression --repository-format docker --project project-mlops12-first-chris-op --location us-central1

## Paso Automatizado
- git init
- git add .
- git commit -m "Proyecto de automatización de despliegue en GCR"
- git remote add origin https://github.com/ChrisO27/mlops12-streamlit-regresion.git
- git branch -M main
- git push -u origin main









# SE REPITE DENUEVO PARA SUBIR UN CAMBIO 

## Paso 2: Crear la imagen de mi APLICACION y subir al repositoriocle
gcloud builds submit --config=cloudbuild.yaml --project project-mlops12-first-chris-op

## Paso 3: Comando para despliegue o ejecución de la imagen en el repositorio
gcloud run services replace service.yaml --region us-central1 --project project-mlops12-first-chris-op

## Paso 4: OPCIONAL, Dar permisos de acceso a mi APLICACION. ESTO SE EJECUTA UNA SOLA VEZ
gcloud run services set-iam-policy servicio-streamlit-sesion3-christopher-panana gcr-service-policy.yaml --region us-central1 --project project-mlops12-first-chris-op