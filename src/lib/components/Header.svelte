<script>
  import { user } from '$lib/stores/auth.js';
</script>

<header class="bg-primary text-white py-2 px-4 d-flex justify-content-between align-items-center shadow-sm">
  <!-- Lado izquierdo: Logo y Título -->
  <div class="d-flex align-items-center gap-2">
    <i class="bi bi-briefcase-fill fs-3"></i>
    <h1 class="h4 mb-0 fw-bold">Sistema de Prácticas Profesionales</h1>
  </div>
  
  <!-- Lado derecho: Perfil, Rol y Salir -->
  <div class="d-flex align-items-center gap-3">
    <!-- Enlace directo a Mi Perfil -->
    <a href="/perfil" class="btn btn-light btn-sm fw-bold text-primary shadow-sm rounded-pill px-3">
      <i class="bi bi-person-circle me-1"></i> Mi Perfil
    </a>

    <!-- Badge del rol actual -->
    <span class="badge bg-white text-primary fw-semibold p-2 text-uppercase">{$user.rol}</span>
    
    <!-- Botón de Cerrar Sesión -->
    <a href="/" class="btn btn-outline-light btn-sm rounded-pill px-3">
      <i class="bi bi-box-arrow-right me-1"></i> Salir
    </a>
  </div>
</header>