# Tarea2_Robotica_UMX
Animación 2
clear; clc;

L1 = 10;
L2 = 8;

angulo_hombro_final = 30;
angulo_codo_final = 45;

theta2 = 0;

for theta1 = 0:1:angulo_hombro_final

    x_codo = L1 * cosd(theta1);
    y_codo = L1 * sind(theta1);

    x_mano = x_codo + L2 * cosd(theta1 + theta2);
    y_mano = y_codo + L2 * sind(theta1 + theta2);

    clf;
    hold on;
    grid on;
    axis equal;
    axis([-15 20 -5 20]);

    plot([0 x_codo], [0 y_codo], 'b-o', 'LineWidth', 3);
    plot([x_codo x_mano], [y_codo y_mano], 'r-o', 'LineWidth', 3);
    plot(x_mano, y_mano, 'ko', 'MarkerFaceColor', 'g', 'MarkerSize', 8);

    title(sprintf('Hombro: %d grados | Codo: %d grados', theta1, theta2));
    xlabel('X (cm)');
    ylabel('Y (cm)');

    drawnow;
    pause(0.05);

end

theta1 = angulo_hombro_final;

for theta2 = 0:1:angulo_codo_final

    x_codo = L1 * cosd(theta1);
    y_codo = L1 * sind(theta1);

    x_mano = x_codo + L2 * cosd(theta1 + theta2);
    y_mano = y_codo + L2 * sind(theta1 + theta2);

    clf;
    hold on;
    grid on;
    axis equal;
    axis([-15 20 -5 20]);

    plot([0 x_codo], [0 y_codo], 'b-o', 'LineWidth', 3);
    plot([x_codo x_mano], [y_codo y_mano], 'r-o', 'LineWidth', 3);
    plot(x_mano, y_mano, 'ko', 'MarkerFaceColor', 'g', 'MarkerSize', 8);

    title(sprintf('Hombro: %d grados | Codo: %d grados', theta1, theta2));
    xlabel('X (cm)');
    ylabel('Y (cm)');

    drawnow;
    pause(0.05);

end
