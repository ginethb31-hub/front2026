<!-- src/routes/dashboard/+page.svelte -->
<script>
  import { user, ROLES } from '$lib/stores/auth.js';
</script>

<div class="bg-modulo-dashboard flex-grow-1 py-4">
  <div class="container">
    
    <!-- BANNER INSTITUCIONAL PRINCIPAL -->
    <div class="card border-0 shadow-sm rounded-4 overflow-hidden mb-4 bg-dark text-white position-relative">
      <div class="card-body p-4 p-md-5 position-relative z-1">
        <div class="row align-items-center">
          <div class="col-lg-8">
            <span class="badge bg-primary mb-2 text-uppercase px-3 py-1 rounded-pill" style="font-size: 0.75rem;">Portal Académico de Prácticas</span>
            <h1 class="fw-bold display-6 mb-2">Coordinación de Prácticas Profesionales</h1>
            <p class="text-white-50 mb-0">
              Bienvenido de nuevo, <strong class="text-white">{$user.nombre}</strong>. Panel de control oficial y gestión centralizada para el rol de <span class="badge bg-light text-dark text-uppercase ms-1">{$user.rol}</span>.
            </p>
          </div>
          <div class="col-lg-4 text-lg-end mt-3 mt-lg-0">
            <div class="d-inline-block bg-primary bg-opacity-25 p-3 rounded-circle">
              <i class="bi bi-mortarboard-fill display-5 text-primary"></i>
            </div>
          </div>
        </div>
      </div>
      <div class="position-absolute top-0 end-0 h-100 w-50 bg-primary opacity-10 rounded-start-pill d-none d-lg-block" style="filter: blur(50px);"></div>
    </div>

    <!-- SECCIÓN DE CONTEXTO INSTITUCIONAL EN RECUADROS CON IMÁGENES -->
    <div class="row g-4 mb-4">
      <!-- Tarjeta 1: La Dependencia -->
      <div class="col-md-4">
        <div class="card border-0 shadow-sm rounded-4 h-100 overflow-hidden hover-card">
          <div style="height: 140px; background: url('https://images.unsplash.com/photo-1497366216548-37526070297c?q=80&w=600&auto=format&fit=crop') center/cover no-repeat;" class="position-relative">
            <div class="position-absolute top-0 start-0 w-100 h-100 bg-dark" style="opacity: 0.3;"></div>
            <span class="badge bg-primary position-absolute top-0 start-0 m-3 z-1">Oficina del Egresado</span>
          </div>
          <div class="card-body p-4">
            <h5 class="fw-bold text-dark mb-2">¿Quiénes Somos?</h5>
            <p class="text-dark small mb-0" style="line-height: 1.6; opacity: 0.85;">
              La <strong>Coordinación de Prácticas Profesionales (CPP)</strong> pertenece a la Oficina del Egresado, encargada de la planeación, control y gestión de ubicación de los estudiantes.
            </p>
          </div>
        </div>
      </div>

      <!-- Tarjeta 2: Programas Académicos -->
      <div class="col-md-4">
        <div class="card border-0 shadow-sm rounded-4 h-100 overflow-hidden hover-card">
          <div style="height: 140px; background: url('https://images.unsplash.com/photo-1581091226825-a6a2a5aee158?q=80&w=600&auto=format&fit=crop') center/cover no-repeat;" class="position-relative">
            <div class="position-absolute top-0 start-0 w-100 h-100 bg-dark" style="opacity: 0.3;"></div>
            <span class="badge bg-success position-absolute top-0 start-0 m-3 z-1">Divisiones y Escuelas</span>
          </div>
          <div class="card-body p-4">
            <h5 class="fw-bold text-dark mb-2">Programas Cubiertos</h5>
            <p class="text-dark small mb-0" style="line-height: 1.6; opacity: 0.85;">
              Gestionamos prácticas para estudiantes aptos de Ingenierías, Ciencias Básicas, Arquitectura, Urbanismo, Diseño, Lenguas Modernas y Cultura.
            </p>
          </div>
        </div>
      </div>

      <!-- Tarjeta 3: Relación Universidad - Empresa -->
      <div class="col-md-4">
        <div class="card border-0 shadow-sm rounded-4 h-100 overflow-hidden hover-card">
          <div style="height: 140px; background: url('https://images.unsplash.com/photo-1517245386807-bb43f82c33c4?q=80&w=600&auto=format&fit=crop') center/cover no-repeat;" class="position-relative">
            <div class="position-absolute top-0 start-0 w-100 h-100 bg-dark" style="opacity: 0.3;"></div>
            <span class="badge bg-warning text-dark position-absolute top-0 start-0 m-3 z-1">Alianzas Estratégicas</span>
          </div>
          <div class="card-body p-4">
            <h5 class="fw-bold text-dark mb-2">Universidad – Empresa</h5>
            <p class="text-dark small mb-0" style="line-height: 1.6; opacity: 0.85;">
              Trabajamos constantemente en relaciones que buscan complementar mediante la experiencia real la formación recibida en cada pregrado.
            </p>
          </div>
        </div>
      </div>
    </div>

    <div class="mb-3">
      <h5 class="fw-bold text-dark mb-3"><i class="bi bi-bar-chart-fill text-primary me-2"></i>Resumen y Métricas del Sistema</h5>
    </div>

    <!-- TARJETAS MÉTRICAS SEGÚN EL ROL -->
    <div class="row g-3 mb-4">
      
      {#if $user.rol === ROLES.ESTUDIANTE}
        <div class="col-md-4">
          <div class="card border-0 shadow-sm bg-primary text-white p-3 h-100 hover-card">
            <div class="d-flex justify-content-between align-items-center">
              <div>
                <h6 class="mb-1 text-white-50">Mi Postulación</h6>
                <h3 class="mb-0 fw-bold">En Revisión</h3>
                <small class="text-white-50">Empresa: Software LTDA</small>
              </div>
              <i class="bi bi-send fs-1 opacity-75"></i>
            </div>
          </div>
        </div>
        <div class="col-md-4">
          <div class="card border-0 shadow-sm bg-success text-white p-3 h-100 hover-card">
            <div class="d-flex justify-content-between align-items-center">
              <div>
                <h6 class="mb-1 text-white-50">Bitácoras Enviadas</h6>
                <h3 class="mb-0 fw-bold">4 / 12</h3>
                <small class="text-white-50">Progreso del periodo</small>
              </div>
              <i class="bi bi-journal-check fs-1 opacity-75"></i>
            </div>
          </div>
        </div>
        <div class="col-md-4">
          <div class="card border-0 shadow-sm bg-warning text-dark p-3 h-100 hover-card">
            <div class="d-flex justify-content-between align-items-center">
              <div>
                <h6 class="mb-1 text-muted">Horas Acumuladas</h6>
                <h3 class="mb-0 fw-bold">120 hrs</h3>
                <small class="text-muted">De 380 requeridas</small>
              </div>
              <i class="bi bi-clock-history fs-1 opacity-75"></i>
            </div>
          </div>
        </div>

      {:else if $user.rol === ROLES.TUTOR}
        <div class="col-md-4">
          <div class="card border-0 shadow-sm bg-info text-white p-3 h-100 hover-card">
            <div class="d-flex justify-content-between align-items-center">
              <div>
                <h6 class="mb-1 text-white-50">Estudiantes Asignados</h6>
                <h3 class="mb-0 fw-bold">8</h3>
                <small class="text-white-50">Activos en el periodo</small>
              </div>
              <i class="bi bi-people fs-1 opacity-75"></i>
            </div>
          </div>
        </div>
        <div class="col-md-4">
          <div class="card border-0 shadow-sm bg-warning text-dark p-3 h-100 hover-card">
            <div class="d-flex justify-content-between align-items-center">
              <div>
                <h6 class="mb-1 text-muted">Bitácoras por Revisar</h6>
                <h3 class="mb-0 fw-bold">3</h3>
                <small class="text-muted">Requieren aprobación</small>
              </div>
              <i class="bi bi-journal-text fs-1 opacity-75"></i>
            </div>
          </div>
        </div>
        <div class="col-md-4">
          <div class="card border-0 shadow-sm bg-danger text-white p-3 h-100 hover-card">
            <div class="d-flex justify-content-between align-items-center">
              <div>
                <h6 class="mb-1 text-white-50">Evaluaciones Pendientes</h6>
                <h3 class="mb-0 fw-bold">2</h3>
                <small class="text-white-50">Corte final</small>
              </div>
              <i class="bi bi-clipboard-check fs-1 opacity-75"></i>
            </div>
          </div>
        </div>

      {:else if $user.rol === ROLES.EMPRESA}
        <div class="col-md-4">
          <div class="card border-0 shadow-sm bg-success text-white p-3 h-100 hover-card">
            <div class="d-flex justify-content-between align-items-center">
              <div>
                <h6 class="mb-1 text-white-50">Ofertas Activas</h6>
                <h3 class="mb-0 fw-bold">2</h3>
                <small class="text-white-50">Publicadas en la bolsa</small>
              </div>
              <i class="bi bi-briefcase fs-1 opacity-75"></i>
            </div>
          </div>
        </div>
        <div class="col-md-4">
          <div class="card border-0 shadow-sm bg-primary text-white p-3 h-100 hover-card">
            <div class="d-flex justify-content-between align-items-center">
              <div>
                <h6 class="mb-1 text-white-50">Candidatos Postulados</h6>
                <h3 class="mb-0 fw-bold">15</h3>
                <small class="text-white-50">Hojas de vida recibidas</small>
              </div>
              <i class="bi bi-person-lines-fill fs-1 opacity-75"></i>
            </div>
          </div>
        </div>
        <div class="col-md-4">
          <div class="card border-0 shadow-sm bg-dark text-white p-3 h-100 hover-card">
            <div class="d-flex justify-content-between align-items-center">
              <div>
                <h6 class="mb-1 text-white-50">Practicantes Vinculados</h6>
                <h3 class="mb-0 fw-bold">1</h3>
                <small class="text-white-50">En desarrollo de práctica</small>
              </div>
              <i class="bi bi-building-check fs-1 opacity-75"></i>
            </div>
          </div>
        </div>

      {:else if $user.rol === ROLES.ADMINISTRADOR}
        <div class="col-md-3">
          <div class="card border-0 shadow-sm bg-primary text-white p-3 h-100 hover-card">
            <div class="d-flex justify-content-between align-items-center">
              <div>
                <h6 class="mb-1 text-white-50">Total Usuarios</h6>
                <h3 class="mb-0 fw-bold">124</h3>
                <small class="text-white-50">Activos en plataforma</small>
              </div>
              <i class="bi bi-people fs-1 opacity-75"></i>
            </div>
          </div>
        </div>
        <div class="col-md-3">
          <div class="card border-0 shadow-sm bg-warning text-dark p-3 h-100 hover-card">
            <div class="d-flex justify-content-between align-items-center">
              <div>
                <h6 class="mb-1 text-muted">Empresas Aliadas</h6>
                <h3 class="mb-0 fw-bold">18</h3>
                <small class="text-muted">Convenios vigentes</small>
              </div>
              <i class="bi bi-building fs-1 opacity-75"></i>
            </div>
          </div>
        </div>
        <div class="col-md-3">
          <div class="card border-0 shadow-sm bg-success text-white p-3 h-100 hover-card">
            <div class="d-flex justify-content-between align-items-center">
              <div>
                <h6 class="mb-1 text-white-50">Prácticas Activas</h6>
                <h3 class="mb-0 fw-bold">45</h3>
                <small class="text-white-50">En curso este semestre</small>
              </div>
              <i class="bi bi-journal-check fs-1 opacity-75"></i>
            </div>
          </div>
        </div>
        <div class="col-md-3">
          <div class="card border-0 shadow-sm bg-secondary text-white p-3 h-100 hover-card">
            <div class="d-flex justify-content-between align-items-center">
              <div>
                <h6 class="mb-1 text-white-50">Egresados</h6>
                <h3 class="mb-0 fw-bold">89</h3>
                <small class="text-white-50">Histórico de procesos</small>
              </div>
              <i class="bi bi-mortarboard fs-1 opacity-75"></i>
            </div>
          </div>
        </div>
      {/if}

    </div>

    <!-- SECCIÓN INFORMATIVA Y ACCESOS RÁPIDOS -->
    <div class="row g-4">
      
      <!-- Columna Izquierda: Accesos Rápidos Mejorados -->
      <div class="col-lg-8">
        <div class="card border-0 shadow-sm rounded-4 h-100">
          <div class="card-header bg-white fw-bold py-3 border-0">
            <i class="bi bi-lightning-charge-fill text-warning me-2"></i>Acciones Rápidas del Sistema
          </div>
          <div class="card-body">
            <div class="row g-3">
              {#if $user.rol === ROLES.ESTUDIANTE}
                <div class="col-sm-6">
                  <a href="/postulaciones" class="p-3 border rounded-3 d-block text-decoration-none text-dark bg-light hover-action h-100">
                    <i class="bi bi-search fs-3 text-primary mb-2 d-block"></i>
                    <h6 class="fw-bold mb-1">Ver Ofertas Disponibles</h6>
                    <p class="text-muted small mb-0">Explora las vacantes de prácticas publicadas por empresas aliadas.</p>
                  </a>
                </div>
                <div class="col-sm-6">
                  <a href="/bitacoras" class="p-3 border rounded-3 d-block text-decoration-none text-dark bg-light hover-action h-100">
                    <i class="bi bi-plus-circle fs-3 text-success mb-2 d-block"></i>
                    <h6 class="fw-bold mb-1">Registrar Bitácora</h6>
                    <p class="text-muted small mb-0">Sube tus avances semanales y horas acumuladas de práctica.</p>
                  </a>
                </div>
              {:else if $user.rol === ROLES.TUTOR}
                <div class="col-sm-6">
                  <a href="/bitacoras" class="p-3 border rounded-3 d-block text-decoration-none text-dark bg-light hover-action h-100">
                    <i class="bi bi-journal-check fs-3 text-info mb-2 d-block"></i>
                    <h6 class="fw-bold mb-1">Revisar Bitácoras</h6>
                    <p class="text-muted small mb-0">Evalúa y aprueba los reportes semanales de tus practicantes.</p>
                  </a>
                </div>
                <div class="col-sm-6">
                  <a href="/evaluaciones" class="p-3 border rounded-3 d-block text-decoration-none text-dark bg-light hover-action h-100">
                    <i class="bi bi-clipboard-data fs-3 text-danger mb-2 d-block"></i>
                    <h6 class="fw-bold mb-1">Evaluar Practicante</h6>
                    <p class="text-muted small mb-0">Realiza la calificación de desempeño del periodo actual.</p>
                  </a>
                </div>
              {:else if $user.rol === ROLES.EMPRESA}
                <div class="col-sm-6">
                  <a href="/postulaciones" class="p-3 border rounded-3 d-block text-decoration-none text-dark bg-light hover-action h-100">
                    <i class="bi bi-briefcase fs-3 text-success mb-2 d-block"></i>
                    <h6 class="fw-bold mb-1">Crear Nueva Oferta</h6>
                    <p class="text-muted small mb-0">Publica una nueva vacante para atraer talento universitario.</p>
                  </a>
                </div>
                <div class="col-sm-6">
                  <a href="/empresas" class="p-3 border rounded-3 d-block text-decoration-none text-dark bg-light hover-action h-100">
                    <i class="bi bi-gear fs-3 text-warning mb-2 d-block"></i>
                    <h6 class="fw-bold mb-1">Perfil Institucional</h6>
                    <p class="text-muted small mb-0">Actualiza los datos de contacto y convenios de tu empresa.</p>
                  </a>
                </div>
              {:else if $user.rol === ROLES.ADMINISTRADOR}
                <div class="col-sm-4">
                  <a href="/usuarios" class="p-3 border rounded-3 d-block text-decoration-none text-dark bg-light hover-action h-100">
                    <i class="bi bi-person-plus fs-3 text-info mb-2 d-block"></i>
                    <h6 class="fw-bold mb-1">Crear Usuario</h6>
                    <p class="text-muted small mb-0">Gestiona cuentas y roles en el sistema.</p>
                  </a>
                </div>
                <div class="col-sm-4">
                  <a href="/empresas" class="p-3 border rounded-3 d-block text-decoration-none text-dark bg-light hover-action h-100">
                    <i class="bi bi-building-add fs-3 text-warning mb-2 d-block"></i>
                    <h6 class="fw-bold mb-1">Registrar Empresa</h6>
                    <p class="text-muted small mb-0">Da de alta nuevas empresas aliadas.</p>
                  </a>
                </div>
                <div class="col-sm-4">
                  <a href="/practicas" class="p-3 border rounded-3 d-block text-decoration-none text-dark bg-light hover-action h-100">
                    <i class="bi bi-journal-plus fs-3 text-primary mb-2 d-block"></i>
                    <h6 class="fw-bold mb-1">Asignar Práctica</h6>
                    <p class="text-muted small mb-0">Vincula estudiantes con tutores y empresas.</p>
                  </a>
                </div>
              {/if}
            </div>
          </div>
        </div>
      </div>

      <!-- Columna Derecha: Avisos Institucionales -->
      <div class="col-lg-4">
        <div class="card border-0 shadow-sm rounded-4 h-100">
          <div class="card-header bg-white fw-bold py-3 border-0">
            <i class="bi bi-info-circle-fill text-primary me-2"></i>Avisos y Convocatorias
          </div>
          <div class="card-body">
            <div class="mb-3 pb-3 border-bottom">
              <span class="badge bg-danger-subtle text-danger mb-1 px-2 py-1 rounded">Importante</span>
              <h6 class="fw-bold mb-1 text-dark" style="font-size: 0.95rem;">Cierre de entregas de bitácoras</h6>
              <p class="text-muted small mb-0">Recuerda subir tus reportes semanales antes del viernes a las 11:59 PM.</p>
            </div>
            <div class="mb-0">
              <span class="badge bg-success-subtle text-success mb-1 px-2 py-1 rounded">Nuevos Convenios</span>
              <h6 class="fw-bold mb-1 text-dark" style="font-size: 0.95rem;">Empresas de tecnología aliadas</h6>
              <p class="text-muted small mb-0">Se han habilitado 5 nuevas plazas para prácticas en desarrollo de software.</p>
            </div>
          </div>
        </div>
      </div>

    </div>

  </div>
</div>

<style>
  .hover-card {
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }
  .hover-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 .5rem 1rem rgba(0,0,0,.15)!important;
  }
  .hover-action {
    transition: all 0.2s ease-in-out;
  }
  .hover-action:hover {
    background-color: #fff !important;
    border-color: #0d6efd !important;
    transform: translateY(-2px);
    box-shadow: 0 .25rem .5rem rgba(0,0,0,.075);
  }
</style>