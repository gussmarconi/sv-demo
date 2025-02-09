<script>
	import { onMount } from 'svelte';

	let formData = {
		dbType: '',
		dbVersion: '',
		dbName: '',
		ipAddress: '',
		port: '',
		haInstallation: false,
		appConnection: false,
		environment: '',
		features: {
			audit: false,
			security: false,
			masking: false,
			vulnerabilityAnalysis: false,
			monitoring: false,
			reports: false
		},
		contact: {
			name: '',
			email: '',
			phone: '',
			position: '',
			entity: ''
		}
	};

	function formatJSON(data) {
		return {
			body: {
				tipo_base_datos: data.dbType,
				version: data.dbVersion,
				nombre_base_datos: data.dbName,
				direccion_ip: data.ipAddress,
				puerto: data.port,
				instalacion_ha: data.haInstallation,
				conectar_app: data.appConnection,
				ambiente_instalacion: data.environment,
				funcionalidades_poc: Object.keys(data.features).filter(key => data.features[key]),
				nombre_apellido: data.contact.name,
				email: data.contact.email,
				telefono: data.contact.phone,
				cargo: data.contact.position,
				entidad: data.contact.entity
			}
		};
	}

	async function handleSubmit() {
		try {
			const formattedData = formatJSON(formData);
			const response = await fetch('https://4nofs54927.execute-api.us-east-1.amazonaws.com/test2/contactus-rest-api', {
				method: 'POST',
				headers: {
					'Content-Type': 'application/json'
				},
				body: JSON.stringify(formattedData)
			});
			const result = await response.json();
			console.log(result);
		} catch (error) {
			console.error('Error:', error);
		}
	}
</script>

<div class="m-40 flex flex-row">
	<div class="mr-6 basis-1/3 border-solid border-2 border-orange-600 rounded-lg p-2 pb-12 ">
		Requisitos
		<div>
			<span class="label-text">Hasta 6000 operaciones/segundo</span>
			<ul>
				<li>
					<span class="label-text"
						>- Máquina Virtual Linux (OS: Ubuntu 22, RHEL 8, RHEL 9, consultar para validar otras
						distros)</span
					>
				</li>
				<li><span class="label-text">- CPU: 2 Cores</span></li>
				<li><span class="label-text">- RAM: 4GB</span></li>
				<li>
					<span class="label-text"
						>- Storage: 120GB (20GB para el Sistema + 100GB Almacenamiento de para Diccionario de
						Datos y Auditoria)</span
					>
				</li>
				<li>
					<span class="label-text"
						>- Conectividad de red (Dirección IP, puerto 11000, 11001 (DataSunrise) y puerto Base de
						Datos)</span
					>
				</li>
			</ul>
		</div>
	</div>

	<div class="basis-2/3 border-solid border-2 border-blue-600 rounded-lg p-2 pb-12 ">
		Formulario
		<div>
			Elementos Formulario
			<div>
				Base de Datos
				<div class="flex flex-row">
					<div class="mr-3 w-1/6">
						<label class="label">
							<span class="label-text">Tipo de Base de Datos</span>
							<select class="select" bind:value={formData.dbType}>
								<option value="1">MSSQL</option>
								<option value="2">MySQL</option>
								<option value="3">Oracle</option>
								<option value="4">PostgresQL</option>
							</select>
						</label>
					</div>
					<div class="mr-3 w-1/6">
						<label class="label">
							<span class="label-text">Versión</span>
							<select class="select" bind:value={formData.dbVersion}>
								<option value="1">v1</option>
								<option value="2">v2</option>
								<option value="3">v3</option>
								<option value="4">v4</option>
							</select>
						</label>
					</div>
					<div class="mr-3 w-2/6">
						<label class="label">
							<span class="label-text">Nombre Base de Datos</span>
							<input class="input" type="text" placeholder="Nombre Base de Datos" bind:value={formData.dbName} />
						</label>
					</div>
					<div class="mr-3 w-1/6">
						<label class="label">
							<span class="label-text">Dirección IP</span>
							<input class="input" type="text" placeholder="Dirección IP" bind:value={formData.ipAddress} />
						</label>
					</div>
					<div class="mr-3 w-1/6">
						<label class="label">
							<span class="label-text">Puerto</span>
							<input class="input" type="text" placeholder="Puerto" bind:value={formData.port} />
						</label>
					</div>
				</div>
				<div class="mt-4 flex flex-row">
					<div class="mr-3 w-1/4">
						<label class="flex items-center space-x-2">
							<p>Se Requiere Instalación en HA</p>
							<input class="checkbox" type="checkbox" bind:checked={formData.haInstallation} />
						</label>
					</div>
					<div class="mr-3 w-1/4">
						<label class="flex items-center space-x-2">
							<p>Se conectará alguna aplicación a DS</p>
							<input class="checkbox" type="checkbox" bind:checked={formData.appConnection} />
						</label>
					</div>
					<div class="mr-3 w-2/4">
						<label class="flex items-center space-x-2">
							<p>En que ambiente se realizará la instalación:</p>
							<select class="select" bind:value={formData.environment}>
								<option value="1">Producción</option>
								<option value="2">Desarrollo (recomendado)</option>
								<option value="3">QA</option>
								<option value="4">Otro</option>
							</select>
						</label>
					</div>
				</div>
				<div class="flex flex-col">
					<div><span class="label-text">Funcionalidades a Probar en la PoC:</span></div>
					<div class="flex flex-row">
						<div class="mr-3 w-1/6">
							<label class="flex items-center space-x-2">
								<p>Auditoría</p>
								<input class="checkbox" type="checkbox" bind:checked={formData.features.audit} />
							</label>
						</div>
						<div class="mr-3 w-1/6">
							<label class="flex items-center space-x-2">
								<p>Seguridad</p>
								<input class="checkbox" type="checkbox" bind:checked={formData.features.security} />
							</label>
						</div>
						<div class="mr-3 w-1/6">
							<label class="flex items-center space-x-2">
								<p>Enmascaramiento</p>
								<input class="checkbox" type="checkbox" bind:checked={formData.features.masking} />
							</label>
						</div>
						<div class="mr-3 w-1/6">
							<label class="flex items-center space-x-2">
								<p>Análisis de Vulnerabilidades</p>
								<input class="checkbox" type="checkbox" bind:checked={formData.features.vulnerabilityAnalysis} />
							</label>
						</div>
						<div class="mr-3 w-1/6">
							<label class="flex items-center space-x-2">
								<p>Monitoreo</p>
								<input class="checkbox" type="checkbox" bind:checked={formData.features.monitoring} />
							</label>
						</div>
						<div class="mr-3 w-1/6">
							<label class="flex items-center space-x-2">
								<p>Reportes</p>
								<input class="checkbox" type="checkbox" bind:checked={formData.features.reports} />
							</label>
						</div>
					</div>
				</div>
			</div>

			<p class="opacity-60 type-scale-1"></p>
			<hr class="hr" />

			<div>Datos Contacto</div>
			<div>
				<div class="flex flex-row">
					<div class="mr-3 w-2/5">
						<label class="label">
							<span class="label-text">Nombre y Apellido</span>
							<input class="input" type="text" placeholder="Nombre y Apellido" bind:value={formData.contact.name} />
						</label>
					</div>

					<div class="mr-3 w-2/5">
						<label class="label">
							<span class="label-text">Email</span>
							<input class="input" type="text" placeholder="Email" bind:value={formData.contact.email} />
						</label>
					</div>
					<div class="mr-3 w-1/5">
						<label class="label">
							<span class="label-text">Teléfono</span>
							<input
								class="input [&::-webkit-inner-spin-button]:appearance-none"
								type="number"
								placeholder="Teléfono"
								bind:value={formData.contact.phone}
							/>
						</label>
					</div>
				</div>
				<div class="flex flex-row">
					<div class="mr-3 w-1/2">
						<label class="label">
							<span class="label-text">Cargo</span>
							<input class="input" type="text" placeholder="Cargo" bind:value={formData.contact.position} />
						</label>
					</div>
					<div class="mr-3 w-1/2">
						<label class="label">
							<span class="label-text">Entidad</span>
							<input class="input" type="text" placeholder="Entidad" bind:value={formData.contact.entity} />
						</label>
					</div>
				</div>
			</div>
			<div class="mt-4 relative">
				<button class="btn preset-filled-primary-500 absolute inset-y-0 right-0 w-16 mr-3" on:click={handleSubmit}>Enviar</button>
			</div>
		</div>
	</div>
</div>
