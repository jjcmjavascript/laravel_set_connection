# laravel_set_connection


    public function tipooperacion()
    {
        $instance = $this->setConnection('mysql')
            ->newRelatedInstance('App\Recepcion\TipoOperacion');

        return new BelongsTo(
            $instance->newQuery(),
            $this, 'id_tipo_operacion',
            'id_recepcion_tipo_operacion',
            null
        );
    }

    public function recepcion()
    {
        $instance = $this->setConnection('mysql')->newRelatedInstance('App\Recepcion\Recepcion');
        return new hasOne($instance->newQuery(), $this, 'id_online', 'id_recepcion_iniciativa', null);
        // return $this->hasOne(
        //     'App\Recepcion\Recepcion',
        //     'id_online',
        //     'id_recepcion_iniciativa'
        // );
    }
