<script>
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
							<select class="select">
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
							<select class="select">
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
							<input class="input" type="text" placeholder="Nombre Base de Datos" />
						</label>
					</div>
					<div class="mr-3 w-1/6">
						<label class="label">
							<span class="label-text">Dirección IP</span>
							<input class="input" type="text" placeholder="Dirección IP" />
						</label>
					</div>
					<div class="mr-3 w-1/6">
						<label class="label">
							<span class="label-text">Puerto</span>
							<input class="input" type="text" placeholder="Puerto" />
						</label>
					</div>
				</div>
				<div class="mt-4 flex flex-row">
					<div class="mr-3 w-1/4">
						<label class="flex items-center space-x-2">
							<p>Se Requiere Instalación en HA</p>
							<input class="checkbox" type="checkbox" />
						</label>
					</div>
					<div class="mr-3 w-1/4">
						<label class="flex items-center space-x-2">
							<p>Se conectará alguna aplicación a DS</p>
							<input class="checkbox" type="checkbox" />
						</label>
					</div>
					<div class="mr-3 w-2/4">
						<label class="flex items-center space-x-2">
							<p>En que ambiente se realizará la instalación:</p>
							<select class="select">
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
								<input class="checkbox" type="checkbox" />
							</label>
						</div>
						<div class="mr-3 w-1/6">
							<label class="flex items-center space-x-2">
								<p>Seguridad</p>
								<input class="checkbox" type="checkbox" />
							</label>
						</div>
						<div class="mr-3 w-1/6">
							<label class="flex items-center space-x-2">
								<p>Enmascaramiento</p>
								<input class="checkbox" type="checkbox" />
							</label>
						</div>
						<div class="mr-3 w-1/6">
							<label class="flex items-center space-x-2">
								<p>Análisis de Vulnerabilidades</p>
								<input class="checkbox" type="checkbox" />
							</label>
						</div>
						<div class="mr-3 w-1/6">
							<label class="flex items-center space-x-2">
								<p>Monitoreo</p>
								<input class="checkbox" type="checkbox" />
							</label>
						</div>
						<div class="mr-3 w-1/6">
							<label class="flex items-center space-x-2">
								<p>Reportes</p>
								<input class="checkbox" type="checkbox" />
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
							<input class="input" type="text" placeholder="Nombre y Apellido" />
						</label>
					</div>

					<div class="mr-3 w-2/5">
						<label class="label">
							<span class="label-text">Email</span>
							<input class="input" type="text" placeholder="Email" />
						</label>
					</div>
					<div class="mr-3 w-1/5">
						<label class="label">
							<span class="label-text">Teléfono</span>
							<input
								class="input [&::-webkit-inner-spin-button]:appearance-none"
								type="number"
								placeholder="Teléfono"
							/>
						</label>
					</div>
				</div>
				<div class="flex flex-row">
					<div class="mr-3 w-1/2">
						<label class="label">
							<span class="label-text">Cargo</span>
							<input class="input" type="text" placeholder="Cargo" />
						</label>
					</div>
					<div class="mr-3 w-1/2">
						<label class="label">
							<span class="label-text">Entidad</span>
							<input class="input" type="text" placeholder="Entidad" />
						</label>
					</div>
				</div>
			</div>
			<div class="mt-4 relative">
				<button class="btn preset-filled-primary-500 absolute inset-y-0 right-0 w-16 mr-3">Enviar</button>
			</div>
		</div>
	</div>
</div>
